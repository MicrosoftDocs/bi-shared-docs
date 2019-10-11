---
title: SQL Server Analysis Services Cube processing fails with Operation canceled HY008 error | Microsoft Docs
description: This article describes background troubleshooting information and specific steps for one error that can occur when using SQL Server Analysis Services when processing multi-dimensional models.
author: ramakoni1
ms.author: Jason.Howell
ms.reviewer: MashaMSFT
ms.services: analysis-services
ms.topic: troubleshooting blog
ms.date: 04/13/2019
---

# Troubleshoot Analysis Services Cube Processing Error "OLE DB error: OLE DB or ODBC error: Operation canceled; HY008."

This article describes background troubleshooting information and specific steps for one error that can occur when using SQL Server Analysis Services and processing multi-dimensional models.

> [!NOTE]
> This article is derived from a blog posted on 6/11/2012, and may contain dated material.

## Errors During Processing

Analysis Services processing may fail with this error:
`OLE DB error: OLE DB or ODBC error: Operation canceled; HY008.`

In SQL OLEDB terms `HY008` means `DB_E_CANCELED`, suggesting the query was canceled purposefully by the caller. At times, you can see this better error from Management Studio:

```Error output
Internal error: The operation terminated unsuccessfully.
OLE DB error: OLE DB or ODBC error: Query timeout expired;HYT00.
Errors in the OLAP storage engine: An error occurred while the dimension, with the ID of '<Some ID>', Name of '<Dimension Name>' was being processed.
```

![SQL Server Management Studio process progress showing an error](media\analysis-services-cube-processing-fails-with-error\8741.image_thumb_39C769A7.png)

`HYT00` means `DB_E_ABORTLIMITREACHED (0x80040E31)` or a timeout expired. The timeout expired due to the SQL_QUERY_TIMEOUT setting. The command timeout or query timeout kicked in to kill the running query and cancel the work.

### XMLA Equivalent Command and Errors

If you use XMLA commands to process your Analysis Services objects, the syntax may resemble the following example:

```XMLA
<Batch xmlns="http://schemas.microsoft.com/analysisservices/2003/engine">
    <Parallel>
        <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ddl2="http://schemas.microsoft.com/analysisservices/2003/engine/2" xmlns:ddl2_2="http://schemas.microsoft.com/analysisservices/2003/engine/2/2" xmlns:ddl100_100="http://schemas.microsoft.com/analysisservices/2008/engine/100/100" xmlns:ddl200="http://schemas.microsoft.com/analysisservices/2010/engine/200" xmlns:ddl200_200="http://schemas.microsoft.com/analysisservices/2010/engine/200/200" xmlns:ddl300="http://schemas.microsoft.com/analysisservices/2011/engine/300" xmlns:ddl300_300="http://schemas.microsoft.com/analysisservices/2011/engine/300/300">
            <Object>
                <DatabaseID>AdventureWorksDW2012Multidimensional-EE</DatabaseID>
            </Object>
            <Type>ProcessFull</Type>
            <WriteBackTableCreation>UseExisting</WriteBackTableCreation>
        </Process>
    </Parallel>
</Batch>
```

When a timeout occurs, the system shows a list of different errors appended in a long string. One or several of the database connections have a timeout, but you may not notice. There is significant noise in the error the multiple connections get a cancellation notification. Analysis Services reports the errors in a seemingly random order due to the multi-threaded nature of the processing implementation. The time-out indicator is hard to see.

```output
Internal error: The operation terminated unsuccessfully. Internal error: The operation terminated unsuccessfully. Server: The current operation was cancelled because another operation in the transaction failed. Internal error: The operation terminated unsuccessfully. OLE DB error: OLE DB or ODBC error: **Communication link failure; 08S01; Shared Memory Provider: No process is on the other end of the pipe.
; 08S01.** Errors in the OLAP storage engine: An error occurred while the dimension, with the ID of 'Dim Time', Name of 'Date' was being processed. Errors in the OLAP storage engine: An error occurred while the 'Fiscal Year' attribute of the 'Date' dimension from the 'AdventureWorksDW2012Multidimensional-EE' database was being processed. OLE DB error: OLE DB or ODBC error: Communication link failure; 08S01; Shared Memory Provider: No process is on the other end of the pipe.  
```

To understand this output, `08S01` means `DB_E_CANNOTCONNECT` from the provider. This HResult is a bit of a misnomer. It could be that the system can’t connect, or it's been disconnected or canceled by the provider or the server if the query was canceled.

Check the `OLAP\Log\Msmdsrv.log` file. You might get the error message in case your application didn't log it.

```msmdsrv.log
(6/12/2012 4:52:21 PM) Message:  (Source: [\\?\C:\OLAP\Log\msmdsrv.log](file://\\?\C:\OLAP\Log\msmdsrv.log), Type: 3, Category: 289, Event ID: 0xC1210003)
(6/12/2012 4:52:21 PM) Message: OLE DB error: OLE DB or ODBC error: Operation canceled; HY008. (Source: [\\?\C:\OLAP\Log\msmdsrv.log](file://\\?\C:\OLAP\Log\msmdsrv.log), Type: 3, Category: 289, Event ID: 0xC1210003)
(6/12/2012 4:52:22 PM) Message: OLE DB error: OLE DB or ODBC error: Operation canceled; HY008. (Source: [\\?\C:\OLAP\Log\msmdsrv.log](file://\\?\C:\OLAP\Log\msmdsrv.log), Type: 3, Category: 289, Event ID: 0xC1210003)
(6/12/2012 4:52:24 PM) Message: OLE DB error: OLE DB or ODBC error: Operation canceled; HY008. (Source: [\\?\C:\OLAP\Log\msmdsrv.log](file://\\?\C:\OLAP\Log\msmdsrv.log), Type: 3, Category: 289, Event ID: 0xC1210003)
(6/12/2012 4:45:33 AM) Message: OLE DB error: OLE DB or ODBC error: Operation canceled; HY008. (Source: [\\?\C:\OLAP\Log\msmdsrv.log](file://\\?\C:\OLAP\Log\msmdsrv.log), Type: 3, Category: 289, Event ID: 0xC1210003)
```

The preceding log output indicates that the OLE DB provider reported an error, hex code `0xC1210003`.

### Attempt to Simplify the Error

If you are unable to determine which specific object and attribute is causing the problem, you can simplify the processing parallelism by restricting the number of connections to the relational database.

In **Solution Explorer**, select your **Data Source** properties. Adjust **Maximum number of connections** from value 10 to value 1. Next time you process the objects, any failure may better show  the problem attributes and a more exact error description.

## Background on Cube Processing

When Analysis Services process a cube or a lower level object like a dimension or measure group, it sends many large SQL queries to the relational database engine through an OLE DB provider. For example, `SELECT * FROM DimTABLE1, SELECT * FROM FactTable1`.

These processing queries can take minutes to hours, depending on how many joins are there are and how large the tables (and partitions) are. The number of joins is dependent entirely on your cube design, and your dimension and measure group relationships in the design.

To connect to the relational data source, there are connection strings stored in the cube design to point to the data warehouse in the database server.

![Analysis Services Data Sources](media\analysis-services-cube-processing-fails-with-error\5125.image_thumb_4986FEAB.png)

This is a connection string that gets saved into the AS database design. It can point to SQL Server, or it can point to other third-party relational databases (Teradata, Oracle, etc.) In the following screenshot, the SQL Server 2012 OLE DB provider named **SQLNCLI11.1** is shown.

![Analysis Services Data Source Properties](media\analysis-services-cube-processing-fails-with-error\1884.image_thumb_15725F58.png)

## Background on Command and Connection Timeouts

Whenever a command (a TSQL query in the case of SQL Server) is issued to the data source, the command timeout property is set by the Analysis Services caller.

The following example shows ADO pseudo code to show how a command timeout is set by the code that runs Analysis Services internally:

```pseudocode
conn1.Open();
command = conn1.CreateCommand();
command.CommandText = "Select * from DimTable";
command.CommandTimeout = 15;
```  

In the preceding example, if 15 seconds pass and the query hasn’t yet finished, the OLE DB provider cancels the query on behalf of the caller. The caller doesn’t have to keep any timer because the timeout is set in the provider layer, therefore the caller doesn’t really know if the query fails how long it took and if it was a timeout or not.

In OLE DB terms, this property is called **DBPROP_COMMANDTIMEOUT** on **DBPROPSET_ROWSET** object. This property lets you run queries for a certain amount of time, and if the command doesn’t finish it will be canceled. In SQL Server, you can see such timeouts with an **Attention** event in the profiler trace. In that profiler trace, the event duration will exactly match the duration of the command timeout.

Notice that command timeout setting is not set on the Connection or the connection string itself, so it has to be set after a connection is established, as each command object is used.  There is a similar connection timeout: `DBPROP_INIT_TIMEOUT` on `DBPROPSET_DBINIT` object. In Analysis Services, the connection timeout is a separate property **ExternalConnectionTimeout**. This setting is applicable for making initial contact with the server, checking the authentication and authorization of accounts. This setting does not impact long running queries typically, since the initial connection was successful without failure.

You can control the OLE DB command timeout in the Analysis Services. There is a setting **ExternalCommandTimeout** in the advanced options on the Analysis Services instance. The default value is 60 mins (one hour).  While that's a fairly high timeout value, it may not be long enough. This default configuration allowed any one TSQL query to the relational database lasts 1 hour or more. After that point, the command will be canceled by the OLEDB provider used to connect to that system, and the Analysis services processing command will fail.

**[ExternalCommandTimeout](https://docs.microsoft.com/sql/analysis-services/server-properties/general-properties?view=sql-server-2017)** - An integer property that defines the timeout, in seconds, for commands issued to external servers, including relational data sources and external Analysis Services servers.
The default value for this property is 3600 (seconds).

If you expect the processing queries to take more than 1 hour, then you might raise the timeout even higher than 1 hour. For example, I was working on a cube this week and the processing join queries take around 9 hours to complete on a 2-TB database with some large complex joins.

Right click on the server name in Management Studio > Properties. Then check “Show Advanced (All) Properties”. Then adjust the **ExternalCommandTimeout **setting, as shown in the following images:

![Analysis Services Server Properties](media\analysis-services-cube-processing-fails-with-error\5125.image_thumb_538B7A09.png)

![Analysis Services Properties](media\analysis-services-cube-processing-fails-with-error\2068.image_thumb_7BDAAC5D.png)
  
Now when it runs external queries to talk to the relational database, it will set the Command Timeout to the value specified so that it can run a long time without failure.

## Long Processing Duration Can Lead to Timeouts

In the case where processing queries take more than an hour, consider that there may be ways to tune the system to perform faster.

You could spend time to tune the joins that AS does when it runs all those processing queries in the background on your behalf.

You could partition your measure groups so that the unit of work done by processing is a smaller chunk of data rather than all data at once. However, partitioning requires careful thought and cube design work. If your data has more than 20 million rows in a table, and you see  processing performance problems, then consider partitioning.

## Tune the Relational Database System

After running the cube processing once or twice, you can look for **missing indexes** in the relational database/data warehouse system. Take a few minutes to tune the database. Add some indexes to the relational data warehouse tables to help tune the join criteria to process the cube.

The following T-SQL code is borrowed from the support tool PSSDiag. It identifies the most helpful missing indexes, and works on SQL Server 2005 and beyond. Find the indexes on the fact and dimension tables that help improve the performance the most. Remember that while adding an index may help read performance (like cube processing) it may slow some insert and update performance (ETL activities).

```sql
PRINT 'Missing Indexes: ' PRINT 'The "improvement_measure" column is an indicator of the (estimated) improvement that might ' PRINT 'be seen if the index was created. This is a unitless number, and has meaning only relative ' PRINT 'the same number for other indexes. The measure is a combination of the avg_total_user_cost, ' PRINT 'avg_user_impact, user_seeks, and user_scans columns in sys.dm_db_missing_index_group_stats.' PRINT '' PRINT '-- Missing Indexes --' SELECT CONVERT (varchar, getdate(), 126) AS runtime, mig.index_group_handle, mid.index_handle, CONVERT (decimal (28,1), migs.avg_total_user_cost * migs.avg_user_impact * (migs.user_seeks + migs.user_scans)) AS improvement_measure, 'CREATE INDEX missing_index_' + CONVERT (varchar, mig.index_group_handle) + '_' + CONVERT (varchar, mid.index_handle) + ' ON ' + mid.statement + ' (' + ISNULL (mid.equality_columns,'') + CASE WHEN mid.equality_columns IS NOT NULL AND mid.inequality_columns IS NOT NULL THEN ',' ELSE '' END + ISNULL (mid.inequality_columns, '') + ')' + ISNULL (' INCLUDE (' + mid.included_columns + ')', '') AS create_index_statement, migs.*, mid.database_id, mid.[object_id] FROM sys.dm_db_missing_index_groups mig INNER JOIN sys.dm_db_missing_index_group_stats migs ON migs.group_handle = mig.index_group_handle INNER JOIN sys.dm_db_missing_index_details mid ON mig.index_handle = mid.index_handle WHERE CONVERT (decimal (28,1), migs.avg_total_user_cost * migs.avg_user_impact * (migs.user_seeks + migs.user_scans)) > 10 ORDER BY migs.avg_total_user_cost * migs.avg_user_impact * (migs.user_seeks + migs.user_scans) DESC PRINT '' GO
```

## Memory Competition Impact on Timeouts

There are multiple reasons that timeouts may occur, many include non-timeout scenarios too. The second most common cause of a processing T-SQL query being canceled is out-of-memory failures.

There can be competition for memory between SQL Server Database Engine (SQLServr.exe), Analysis Services(MsMdsrv.exe), Integration Services packages (DTExec.exe / ISServerExec.exe), Reporting Services running on the same machine. Maybe you need to throttle back the other services, or balance memory allocations. The most common being to limit the SQL Server **maximum server memory** setting.

Cube processing is like the most intensive processing time for a SQL Server used as a data warehouse, since the Analysis Services pushes several large queries with complex joins to the SQL relational database engine at the same time.

```sql
exec sp_configure 'show advanced',1;
reconfigure;
exec sp_configure 'min server memory';
exec sp_configure 'max server memory';
-- look at config_value in the results for the current MB setting configured
```

The ETL processes that typically run rarely benefit from the normal buffering of the SQL Server database Engine’s buffer pool. Consider SSIS packages that import large sets of data from a transactional system into a data warehouse system. ETL operations often use BULK INSERT commands that simply don’t require much warm data in memory.

Other ETL operations during the ETL phase of building a data warehouse certainly do benefit from SQL’s large buffer pool. The read (SELECT) and UPDATE and JOIN parts of the ETL processing (such as Lookups and slowly changing dimension updates) use cached warm data in memory if available. Lowering the SQL Server Database Engine’s memory may have a side effect on those parts of the ETL imports that usually go on just before cube processing.

That is, reading data from RAM is 1000-1million times faster than reading from your average spinning disk drive, therefore shrinking the SQL buffer pool means more disk reads, and unless you have high end SSD solid-state disks or a high end SAN you may wait a little more.

### Measuring Memory Consumption in The System

If memory is the culprit, gather a profiler trace and these performance counters to better investigate the cause:

1. Set up Windows performance monitor to produce a trace of resource consumption.

   Start > Run > Perfmon

2. Right click on Counter Logs icon in the tree under Performance Logs, and begin a new counter log. Name the log.

3. Add the counter for the following Objects, ALL counters for each object, ALL instances for each object.

   - Memory
   - MSAS* --- all objects (for a default instances of AS)
   - MSOLAP$InstanceName* --- all objects (for a named instance of AS)
   - MSSQL* --- all objects (for the SQL Database Engine)
   - Paging File
   - Process
   - Processor
   - System
   - Thread

4. Sample every 15 seconds.

5. On Log tab, specify the directory and file name strategy, as a Binary File.

6. To get Perfmon to roll over to a new file once a day, on the Schedule tab, choose:

   - Stop log after: "1 day"
   - When the log file closes: "Start a new log file"

### Review The Performance Monitor Results

1. Look at the SQL Server engine’s counter to see if the **SQL Memory** > **Total Server Memory** was increasing out of control.

2. Look at **Memory** > **Available MBytes** counter to see how much free memory was available to the processes running in Windows.

3. Look at the **Process** > **Private Bytes** for the various executable processes to see how much each takes in comparison.

4. Look at the MSAS/MSOLAP counters. If the usage amount goes above the High KB amount, then Analysis Services would have to trim some of the buffers in memory.

   - Memory Usage KB
   - Memory Limit High KB
   - Memory Limit Low KB
   - Memory Limit Hard KB

   If the **Memory Usage KB** amount exceeds the **Hard KB** limit, then Analysis services may cancel all current work and go into **panic mode** to kill off the memory consumers. Panic mode may manifest itself in similar errors, but usually the error is more descriptive such as `The Operation Has been Cancelled` or  `The session was canceled because it exceeded a timeout setting (session orphaned timeout or session idle timeout) or it exceeded the session memory limit.`

## Parallel Processing Impact on Timeouts

Analysis Services Processing commands can be run in parallel or sequentially. On the processing command syntax, check if you are specifying to run in Sequential order, or running Parallel? Check the SSIS package or XMLA job that runs the processing.

This image shows the settings for SSIS Analysis Services Processing task:
![SSIS Analysis Services Processing Task settings](media\analysis-services-cube-processing-fails-with-error\1067.image_thumb_38AF2E30.png)

This example shows an XMLA command that runs up to eight tasks in parallel:

```xmla
<Batch xmlns="http://schemas.microsoft.com/analysisservices/2003/engine">
  <Parallel MaxParallel="8">
    <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ddl2="http://schemas.microsoft.com/analysisservices/2003/engine/2" xmlns:ddl2_2="http://schemas.microsoft.com/analysisservices/2003/engine/2/2" xmlns:ddl100_100="http://schemas.microsoft.com/analysisservices/2008/engine/100/100" xmlns:ddl200="http://schemas.microsoft.com/analysisservices/2010/engine/200" xmlns:ddl200_200="http://schemas.microsoft.com/analysisservices/2010/engine/200/200" xmlns:ddl300="http://schemas.microsoft.com/analysisservices/2011/engine/300" xmlns:ddl300_300="http://schemas.microsoft.com/analysisservices/2011/engine/300/300">
      <Object>
        <DatabaseID>AdventureWorksDW2012Multidimensional-EE</DatabaseID>
      </Object>
      <Type>ProcessFull</Type>
      <WriteBackTableCreation>UseExisting</WriteBackTableCreation>
    </Process>
  </Parallel>
</Batch>
```

If the system is timing out, you may need to scale back the number of parallel tasks, especially when you manually override default setting **Let the Server decide**.

You may be able to better throttle the system by reducing the **MaxThreads** configuration by 50% and reprocess the objects, so that fewer threads run at once.

In the worst case, run processing in **Sequential** mode to see if the errors go away. The system will take less memory to run a sequence of one task at a time rather than many at once. The tradeoff may be that it runs longer because you can’t push the system hardware to the same throughput limits.  

To learn more about processing best practices, see this great resource: [SQL Server Best Practices Article](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/administrator/cc966525(v=technet.10)).

For more information on the architecture of cube processing, see [Analysis Services 2005 Processing Architecture](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/administrator/ms345142(v=sql.90)).

## Aggregation Memory Impact on Timeouts

There is an advanced setting **AggregationMemoryLimitMax**. For more information, see [this blog post](http://geekswithblogs.net/ManicArchitect/archive/2010/11/02/142558.aspx)

SQL Server Analysis Services uses memory quota to control the number of concurrent jobs. Each job will calculate how much memory it needs to finish the job and request the memory quota based on its estimate. The job will only proceed when the memory quota is granted.  We estimate the quota for aggregation job, the configuration setting that controls the memory usage estimates are  **AggregationMemoryLimitMin** and **AggregationMemoryLimitMax**

To achieve more parallelism for processing, you could take this advice to tune the settings.

## Additional Timeout Settings

**Query Timeout** is another setting on the Data Source. This setting that seems not to apply readily to processing. This setting applies to the connection pool and will help expire idle connections that are no longer needed. However, this setting doesn't apply to the commands that are run during processing or ROLAP commands.

![Analysis Services processing failure](media\analysis-services-cube-processing-fails-with-error\4617.image_thumb_618A1D6C.png)

There are many other timeouts in Analysis Services, such as:

- **ForceCommitTimeout** for processing to kill user queries should MDX queries hold locks that block processing commit.
- **CommitTimeout** for processing to give up if it gets blocked at commit phase
- **ServerTimeout** for queries to time out after some time
- Connection pool settings such as **IdleConnectionTimeout**, **IdleOrphanSessionTimeout**, **MaxIdleSessionTimeout**, **MinIdleSessionTimeout**, **DatabaseConnectionPoolConnectTimeout**, and the ones we discussed **ExternalConnectionTimeout** and **ExternalCommandTimeout**.

## Special Characters

In some situations, the processing timeout error was due to some special characters present in the columns of one of dimension tables. Even [Nulls values](https://www.sqlservercentral.com/blogs/cube-processing-error-hy008) in a dimension column have been observed to cause processing failures.

You may better isolate the problem by processing each object one by one until you find the problem.

For example, while processing the dimension table its throwing the error: `OLE DB error: OLE DB or ODBC error: Operation canceled; HY008.`

Once the user removed the special characters, processing worked as expected.

## Isolate to A Partition

You may be able to further isolate the error to a specific partition. If you have partitioned your cube, there may be a poorly performing query under one of the partitions.

Experiment with the partition query, and test changing from a direct Named Query Table in the Data Source View, into an underlying SQL query instead.

---
title: "Partitions in Analysis Services tabular models | Microsoft Docs"
description: Learn about partitions in Analysis Services tabular models, specifically benefits of partitions and details about partition deployment.
ms.date: 10/19/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Partitions in tabular models

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

Partitions divide portions of data you need to process (refresh) frequently from data that can be processed less frequently. For example, a fact table may include certain row sets that contain data that rarely changes, but other row sets have data that changes often. There's no need to process *all* of the data when only a portion of it needs to be processed.

Partitions work by dividing a table into logical partition objects. Individual partitions, each containing a unique segment of data, can then be incrementally processed either sequentially or in parallel independent of other partitions, or excluded from processing operations altogether.

## Granularity

By default, each table in a model has a single partition. In many cases, such as with fact tables, dividing a table's single partition into multiple partitions can better utilize available resources for processing.

An effective model design and processing strategy utilizes partitions to eliminate unnecessary processor load and memory consumption, while at the same time making certain that data is refreshed often enough to reflect the most recent data from data sources. For example, a tabular model can have a Sales table which includes sales data for the current fiscal year and each of the previous fiscal years. The model's Sales table has the following partitions:  
  
|Partition|Data from|  
|---------------|---------------|  
|Sales2020|Current fiscal year|  
|Sales2019-2010|Fiscal years 2010, 2011, 2012, 2013, 2014, 2015. 2016, 2017, 2018, 2019|  
|SalesOld|All fiscal years prior to the last ten years.|  
  
As new sales data is added for the current 2020 fiscal year, that data must be processed daily to be reflected accurately in the current fiscal year sales data analysis, therefore the Sales2020 partition is processed every night.  
  
There's no need to process data in the Sales2019-2010 partition nightly. However, because sales data for the previous ten fiscal years can still change because of product returns and other adjustments, it must still be processed regularly, therefore data in the Sales2019-2010 partition is processed monthly. Data in the SalesOld partition rarely changes, therefore only processed annually.  
  
When entering the 2021 fiscal year, a new Sales2021 partition is added to the model's Sales table. The Sales2020 partition can then be merged with the Sales2019-2010 partition and renamed to Sales2020-2011. Data from the 2010 fiscal year is eliminated from the Sales2020-2011 partition and moved into the SalesOld partition. All partitions are then processed to reflect changes. This is commonly known as a *rolling-window* pattern - data in each partition is within a predefined date range and incremented as necessary, keeping memory and processing resource use within a predictable range over time.

Granularity is influenced by various factors including how much data is required to be incrementally processed within an acceptable amount of time. For example, if only the last whole day needs to be processed daily, it may be beneficial to use daily granularity. Mixed granularity can be configured for scenarios such as near-real time refresh at low grain coupled with historical, static partitions at higher granularity. This results in fewer partitions, but also increases management overhead to ensure partition ranges are defined correctly.

Partitioning is also effective for tables containing data from more than one data source. Different data sources may update data at different times, which can determine different granularity and processing requirements for the model's table data. For example, an Orders table in a model contains order transactions from two different fact tables, factInternetOrders and factRetailOrders. At the data source, factInternetOrders is updated hourly. factRetailOrders on the other hand is updated only once a day after all retail stores are closed. By creating separate partitions at different granularities in the model Orders table for data imported from both factInternetOrders and factRetailOrders, processing operations on the Orders table can be separated and executed more inline with order data at the data sources.

Each scenario is unique. Be sure to define a granularity for your data model that most effectively divides data into partitions that must be processed often compared to those that don't.

### Partition limits

Regardless of platform, there is no hard limit on the number of partition objects in a model. However, each partition has at least one segment of data with a memory footprint. Too many small partitions can lead to too many small segments. Query performance can be negatively affected when the storage engine has to scan an excessive number of segments. The speed of metadata operations over too many partitions can also adversely affect processing resources.

Create the minimum number of partitions while still effectively meeting your partitioning goals. It's more important to focus an effective partitioning strategy based on granularity, and processing only those partitions with the most relevant changing data within available processing and memory resources at times when user queries are low.

There's also no limit to the amount of data in a partition. While unlikely, a model could have a single table with a single default partition, and that table could contain all of the data in the model. The amount of data in the partition would be limited only by available memory resources for the service plan or hardware.

## Creating and managing partitions

When authoring models with the Tabular model designer in Visual Studio, you create new partitions, edit, merge, or delete partitions in the model workspace database by using Partition Manager. Depending on the compatibility level of the model you're authoring, Partition Manager provides two modes for selecting data to be included in a partition: For tabular 1400 and higher models with structured data sources, partitions are defined by using an Power Query M expression. For example, the following query defines a partition for the 2019 calendar year:

```PowerQuery-M
let
    Source = #"SQL/sqlserver database windows net;Contoso",
    dbo_Sales = Source{[Schema="dbo",Item="Sales"]}[Data],
    #"Filtered Rows" = Table.SelectRows(dbo_Sales, each [OrderDateKey] >= 20190101 and [OrderDateKey] <= 20191231)
in
    #"Filtered Rows"
```

For provider data sources, partitions are defined by using a SQL query. For example,

```sql
SELECT [dbo].[Sales].* FROM [dbo].[Sales]
WHERE (([OrderDateKey] >= '20190101') AND ([OrderDateKey] <= '20191231'))
```

Notice the Filtered Rows argument in the Power Query M expression and the WHERE clause in the SQL statement define exactly one calendar year by using greater than (>), less than (<), and equals (=) operators. When defining partitions, it's important each partition's query define a unique range of data that cannot cause data duplication with other partitions.

### SQL Server Management Studio (SSMS)

After deploying the model, partitions appear as objects in SQL Server Management Studio (SSMS). Create, edit, merge, and delete partitions for a deployed model by using the Partitions dialog box in SSMS, by executing a Tabular Model Scripting Language (TMSL) script, or programmatically by using the Tabular Object Model (TOM).

### Tabular Model Scripting Language (TMSL)

Partitions for a model are defined in the [Partitions object](../tmsl/partitions-object-tmsl.md). In the following example, the Sales2019 partition is defined as:

```json
"partition": {
      "name": "Sales2019",
      "mode": "import",
      "source": {
        "type": "m",
        "expression": [
          "let",
          "    Source = #\"SQL/sqlserver database windows net;Contoso\",",
          "    dbo_Sales = Source{[Schema=\"dbo\",Item=\"Sales\"]}[Data],",
          "    #\"Filtered Rows\" = Table.SelectRows(dbo_Sales, each [OrderDateKey] >= 20190101 and [OrderDateKey] <= 20191231)",
          "in",
          "    #\"Filtered Rows\""
        ]
      },
```

Actions on the Partitions object can be specified in the following TMSL commands:

- [Create](../tmsl/create-command-tmsl.md)
- [CreateOrReplace](../tmsl/createorreplace-command-tmsl.md)
- [Alter](../tmsl/alter-command-tmsl.md)
- [Delete](../tmsl/delete-command-tmsl.md)
- [MergePartitions](../tmsl/mergepartitions-command-tmsl.md)
- [Refresh](../tmsl/refresh-command-tmsl.md)

TMSL scripts can be executed in SQL Server Management Studio, with  PowerShell by running the [Invoke-ASCmd](/powershell/module/sqlserver/invoke-ascmd) command, or by a SQLServer Integration Services (SSIS) [Script task](/sql/integration-services/control-flow/script-task).

For models at 1100 and 1103 compatibility levels, [Analysis Services Scripting Language (ASSL)](../assl/analysis-services-scripting-language-assl-for-xmla.md) is used instead if TMSL.

### Tabular Object Model (TOM)

In the Tabular Object Model, partitions are defined by a Partition class in the Microsoft.AnalysisServices.Tabular namespace. To learn more about programmatic solutions using TOM as an API, see [Create tables, partitions, and columns (TOM)](../tom/create-tables-partitions-and-columns-in-a-tabular-model.md), and [Advanced partitioning strategies](#advanced-partitioning-strategies) later in this article.

For models at 1100 and 1103 compatibility levels, use [Analysis Management Objects (AMO)](../amo/developing-with-analysis-management-objects-amo.md).

## Processing partitions
  
When table data is partitioned, those partitions can then be processed at a time and cadence appropriate for your solution. When a process (refresh) operation is run, a connection to the data source is made using the data source connection. Analysis Services uses the queries specified for each partition to query the data source. New and updated data is loaded into the model tables, relationships and hierarchies are rebuilt, and calculated columns are re-calculated.

When authoring models in Visual Studio, you can manually run process operations on workspace database partitions from the menu or toolbar. For deployed models, processing operations are invoked manually by using the Process Tables dialog in SSMS, by running a script which includes the [Refresh command (TMSL)](../tmsl/refresh-command-tmsl.md), or programmatically by using the Tabular Object Model (TOM).

### Parallel processing

Analysis Services utilizes parallel processing for two or more partitions, increasing processing performance. There are no configuration settings for parallel processing. Parallel processing occurs by default when you Process Table or select multiple partitions for the same table and Process. There are, however, settings that limit parallel processing operations.

#### MaxConnections

By default, each processing operation will connect to and query a data source for each partition. The default maximum number of connections, specified as the **MaxConnections** property to a single data source is **10**. Analysis Services determines the number of concurrent processing operations to be run based on the number of cores and available threads. These threads are shared across the server instance. A single command like process may not receive all the available threads. The threads that do launch for processing, one for each parallel processing operation, can be delayed to stay within the MaxConnections limit.

#### MaxParallelism

By default processing operations run in parallel as much as possible. However, you can choose to process partitions sequentially or in parallel by specifying the **maxParallism** property option with the [Sequence command (TMSL)](../tmsl/sequence-command-tmsl.md). Setting the value to 1 means not parallel - one thread is used for processing. Setting the value to 2 or more specifies a fixed number of threads can be used for parallel processing operations.

#### Monitor

To determine effective use of available threads during process operations,
for Azure Analysis Services, use Azure Metrics Explorer to monitor CommandPoolIdleThreads and CommandPoolBusyThreads. To learn more, see [Monitor server metrics](/azure/analysis-services/analysis-services-monitor). For SQL Server Analysis Services, use Performance Monitor to monitor Processing pool idle non-I/O threads and Processing pool busy non-I/O threads. To learn more, see [Performance counters (SSAS)](../instances/performance-counters-ssas.md).

> [!NOTE]  
> If re-encoding is detected, parallel processing can cause increased use of resources. This is because multiple partition operations need to be interrupted and restarted with the new encoding in-parallel.  

## Advanced partitioning strategies

The [Automated Partition Management for Analysis Services Tabular Models](https://github.com/microsoft/Analysis-Services/blob/master/AsPartitionProcessing/Automated%20Partition%20Management%20for%20Analysis%20Services%20Tabular%20Models.pdf) .pdf article, along with the accompanying [AsPartitionProcessing](https://github.com/microsoft/Analysis-Services/tree/master/AsPartitionProcessing) code sample in GitHub provides both in-depth information and a solution example for the fictitious company, Advenure Works, by using the Tabular Object Model (TOM) to create and manage partitions. Concepts described in this article and project apply to all Analysis Services platforms.

## See also

[Create and manage tabular model partitions](../../analysis-services/tabular-models/create-and-manage-tabular-model-partitions.md)  
[Partitions object (TMSL)](../tmsl/partitions-object-tmsl.md)  
[Create Tables, Partitions, and Columns with the Tabular Object Model (TOM)](../tom/create-tables-partitions-and-columns-in-a-tabular-model.md)  
[Create partitions (tutorial lesson)](../tutorial-tabular-1400/as-lesson-10-create-partitions.md)

---
title: "Analysis Services general properties | Microsoft Docs"
description:  Learn about the available general properties in Analysis Services, like AdminTimeout and ExternalCommandTimeout. 
ms.date: 11/03/2022
ms.service: analysis-services
ms.custom: 
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---

# General properties

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

Analysis Services includes the following server properties. This article describes those properties that are not otherwise included in a specific category such as Filestore, OLAP, or Memory.

## Non-specific category

##### AdminTimeout

A signed 32-bit integer property that defines the administrator timeout in seconds. This is an advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
The default value for this property is zero (0), which indicates there is no timeout.  

::: moniker range="asallproducts-allversions || azure-analysis-services-current || >= sql-analysis-services-2016"
  
##### AllowedBrowsingFolders

Does not apply to Power BI. A string property that specifies in a delimited list the folders that can be browsed when saving, opening, and finding files in Analysis Services dialog boxes. The Analysis Services service account must have read and write permissions to any folders that you add to the list.  

##### AutoSetDefaultInitialCatalog

Does not apply to Power BI. A Boolean property. When set to true, new client connections automatically default to the first catalog (database) the user has permissions to connect to.
When set to false, no initial catalog is specified. Clients must select a default catalog prior to running queries or discover operations against a database on the server. If no default catalog is specified, an error is returned. If Initial Catalog property is specified in the connection string, the default catalog will be applied from this property.

The default value for this property is true.
  
##### BackupDir

Does not apply to Power BI. A string property that identifies the name of the directory where backup files are stored by default in the event a path is not specified as part of the Backup command.  

::: moniker-end

::: moniker range="asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2019"

##### ClientCacheRefreshPolicy

Overrides the **Scheduled cache refresh** setting for all Power BI semantic models. All Live Connect reports will observe the server-level setting irrespective of the model-level setting, or which workspace they reside on.

The default value for this property is -1, which allows all background cache refreshes as specified in the Scheduled cache refresh setting for the model. To discourage all background cache refreshes, specify zero (0).

::: moniker-end

::: moniker range="asallproducts-allversions || azure-analysis-services-current || >= sql-analysis-services-2016"

##### CollationName

Does not apply to Power BI. A string property that identifies the server collation. For more information, see [Languages and Collations &#40;Analysis Services&#41;](../../analysis-services/languages-and-collations-analysis-services.md).

::: moniker-end

##### CommitTimeout

An integer property that specifies how long (in milliseconds) the server will wait to acquire a write lock when committing a transaction. A waiting period is often required because the server must wait for other locks to be released before it can take a write lock that commits the transaction.  
  
The default value for this property is zero (0), which indicates that the server will wait indefinitely. For more information about lock-related properties, see [SQL Server 2008 R2 Analysis Services Operations Guide](/previous-versions/sql/sql-server-2008-r2/hh226085(v=msdn.10)).  

::: moniker range="asallproducts-allversions || azure-analysis-services-current || >= sql-analysis-services-2016"

##### CoordinatorBuildMaxThreads

Does not apply to Power BI. A signed 32-bit integer property that defines the maximum number of threads allocated to building partition indexes. Increase this value in order to speed up partition indexing, at the cost of memory usage. For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](/previous-versions/sql/sql-server-2008-r2/hh226085(v=msdn.10)).  
  
##### CoordinatorCancelCount

Does not apply to Power BI. A signed 32-bit integer property that defines how frequently the server should check whether a Cancel event occurred (based on internal iteration count). Decrease this number in order to check for Cancel more frequently, at the expense of general performance. This property is ignored in tabular server mode.  
  
##### CoordinatorExecutionMode

Does not apply to Power BI. A signed 32-bit integer property that defines the maximum number of parallel operations the server will attempt, including processing and querying operations. Zero (0) indicates that the server will decide, based on an internal algorithm. A positive number indicates the maximum number of operations in total. A negative number, with the sign reversed, indicates the maximum number of operations per processor.  

The default value for this property is -4, which indicates the server is limited to 4 parallel operations per processor. For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](/previous-versions/sql/sql-server-2008-r2/hh226085(v=msdn.10)).  
  
##### CoordinatorQueryMaxThreads

Does not apply to Power BI. A signed 32-bit integer property that defines the maximum number of threads per partition segment during query resolution. The fewer the number of concurrent users, the higher this value can be, at the cost of memory. Conversely, it may need to be lowered if there are a large number of concurrent users.  
  
##### CoordinatorShutdownMode
  
Does not apply to Power BI. A Boolean property that defines coordinator shutdown mode. This is an advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### DataDir

Does not apply to Power BI. A string property that identifies the name of the directory where data is stored.  

::: moniker-end

##### DefaultSegmentRowCount

A VertiPaq property that defines the number of data rows per segment. Every table partition has at least one segment of data. The value must be the power of 2. The default value is 8,388,608 (8\*1024\*1024) rows.

In general, the larger the segment, the better the compression. However, increasing segment size can negatively affect processing time. With very large tables, it's important to test different segment sizes, measuring memory usage to determine optimal compression.

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

##### DeploymentMode

Does not apply to Power BI. Determines the operational context of an Analysis Services server instance. This property is referred to as 'server mode' in dialog boxes, messages, and documentation. This property is configured by SQL Server Setup based on the server mode you selected when installing Analysis Services. This property should be considered internal only, always using the value specified by Setup.  
  
Valid values for this property include the following:  
  
|Value|Description|  
|-----------|-----------------|  
|0|This is the default value. It specifies multidimensional mode, used to service multidimensional databases that use MOLAP, HOLAP, and ROLAP storage, as well as data mining models.|  
|1|Specifies Analysis Services instances that were installed as part of a [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] for SharePoint deployment. Do not change the deployment mode property of Analysis Services instance that is part of a [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] for SharePoint installation. [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] data will no longer run on the server if you change the mode.|  
|2|Specifies Tabular mode used for hosting tabular model databases that use in-memory storage or DirectQuery storage.|  
  
Each mode is exclusive of the other. A server that is configured for tabular mode cannot run Analysis Services databases that contain cubes and dimensions. If the underlying computer hardware can support it, you can install multiple instances of Analysis Services on the same computer and configure each instance to use a different deployment mode. Remember that Analysis Services is a resource intensive application. Deploying multiple instances on the same system is recommended only for high-end servers.  

::: moniker-end

::: moniker range="asallproducts-allversions || azure-analysis-services-current || >= sql-analysis-services-2016"

##### EnableFast1033Locale

Does not apply to Power BI. An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  

::: moniker-end

##### ExternalCommandTimeout

An integer property that defines the timeout, in seconds, for commands issued to external servers, including relational data sources and external Analysis Services servers.  
  
The default value for this property is 3600 (seconds).  
  
##### ExternalConnectionTimeout

An integer property that defines the timeout, in seconds, for creating connections to external servers, including relational data sources and external Analysis Services servers. This property is ignored if a connection timeout is specified on the connection string.  
  
The default value for this property is 60 (seconds).  
  
##### ForceCommitTimeout

An integer property that specifies how long, in milliseconds, a write commit operation should wait before canceling other commands that preceded the current command, including queries in progress. This allows the commit transaction to proceed by canceling lower priority operations, such as queries.  
  
The default value for this property is 30 seconds (30000 milliseconds), which indicates that other commands will not be forced to timeout until the commit transaction has been waiting for 30 seconds. A setting of 0 implies infinite.  

Queries and processes canceled by this event will report the following error message: "`Server: The operation has been canceled`"  

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](/previous-versions/sql/sql-server-2008-r2/hh226085(v=msdn.10)).  
  
> [!IMPORTANT]  
> **ForceCommitTimeout** applies to cube processing commands and to writeback operations.  

::: moniker-end

::: moniker range="asallproducts-allversions || azure-analysis-services-current || >= sql-analysis-services-2016"

##### IdleConnectionTimeout

Does not apply to Power BI. An integer property that specifies a timeout, in seconds, for connections that are inactive.  
  
The default value for this property is zero (0), which indicates that idle connections will not be timed out.  
  
##### IdleOrphanSessionTimeout

Does not apply to Power BI. An integer property that defines how long, in seconds, orphaned sessions will be retained in server memory. An orphaned session is one that no longer has an associated connection. The default is 120 seconds.  
  
##### InstanceVisible

Does not apply to Power BI. A Boolean property that indicates whether the server instance is visible to discover instance requests from SQL Server Browser service. The default is True. If you set it to false, the instance is not visible to SQL Server Browser.  
  
##### Language

Does not apply to Power BI. A string property that defines the language, including error messages and number formatting. This property overrides the CollationName property.  
  
The default value for this property is blank, which indicates that the CollationName property defines the language.  
  
##### LogDir

Does not apply to Power BI. A string property that identifies the name of the directory that contains server logs. This property only applies when disk files are used for logging, as opposed to database tables (the default behavior).  
  
##### MaxIdleSessionTimeout

Does not apply to Power BI. An integer property that defines the maximum idle session timeout, in seconds. The default is zero (0), indicating that sessions are never timed out. However, idle sessions will still be removed if the server is under resource constraints.  

##### MinIdleSessionTimeout

Does not apply to Power BI. An integer property that defines the minimum time, in seconds, that idle sessions will timeout. The default is 2700 seconds. After this time expires, the server is permitted to end the idle session, but will only do so as memory is needed.  
  
##### Port

Does not apply to Power BI. An integer property that defines the port number on which server will listen for client connections. If not set, server dynamically finds first unused port.  
  
The default value for this property is zero (0), which in turn defaults to port 2383. For more information about port configuration, see [Configure the Windows Firewall to Allow Analysis Services Access](../../analysis-services/instances/configure-the-windows-firewall-to-allow-analysis-services-access.md).  

::: moniker-end

##### ServerTimeout

An integer that defines the timeout, in seconds, for queries. The default is 3600 seconds (or 60 minutes). Zero (0) specifies that no queries will timeout.  

In Power BI, reports will override the default with a much smaller timeout for each of the queries to the capacity. Typically, it is approximately 3 minutes.

::: moniker range="asallproducts-allversions || azure-analysis-services-current || >= sql-analysis-services-2016"

##### TempDir

Does not apply to Power BI. A string property that specifies the location for storing temporary files used during processing, restoring, and other operations. The default value for this property is determined by setup. If not specified, the default is the Data directory.  
  
## RequestPrioritization category

##### Enabled

Does not apply to Power BI. An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### StatisticsStoreSize

Does not apply to Power BI. An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  

::: moniker-end

## See also
  
[Server properties in Analysis Services](../../analysis-services/server-properties/server-properties-in-analysis-services.md)   
[Determine the server mode of an Analysis Services instance](../../analysis-services/instances/determine-the-server-mode-of-an-analysis-services-instance.md)  


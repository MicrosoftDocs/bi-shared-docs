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

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

Partitions divide a table into logical parts. Each partition can then be processed (refreshed) independent of other partitions. By default, each table in a model has one partition, and that partition includes all of the data in the table. A refresh on that one partition is a refresh on the entire table. For a small amount of data, refreshing an entire table can be a low cost operation, requiring only a small amount of memory and processing resources. But for larger models, dividing a table into multiple partitions is the most effective way to ensure you're using valuable memory and processing resources efficiently.

Partitions created by using the Partitions dialog box in Visual Studio during model authoring apply to the model workspace database. When the model is deployed, the partitions defined for the model are created in the deployed model database. You can further create and manage partitions for a deployed model database by using the Partitions dialog box in SQL Server Management Studio (SSMS) or by scripting with the Tabular Object Model (TOM) or Tabular Model Scripting Language (TMSL). Information provided in this article describes partitions created during model authoring by using the Partition Manager dialog box in Visual Studio. To learn more about creating and managing partitions for a deployed model, see [Create and manage tabular model partitions](../../analysis-services/tabular-models/create-and-manage-tabular-model-partitions.md).  
  
## Benefits

Partitions in tabular models divide a table into logical partition objects. Each partition can then be processed independent of other partitions. For example, a table may include certain row sets that contain data that rarely changes, but other row sets have data that changes often. There's is no need to process all of the data when you really just want to process a portion of the data. Partitions enable you to divide portions of data you need to process frequently from the data that can be processed less frequently.  

Effective model design utilizes partitions to eliminate unnecessary processing and subsequent processor load, while at the same time, making certain that data is processed and refreshed often enough to reflect the most recent data from data sources. For example, a tabular model can have a Sales table which includes sales data for the current 2011 fiscal year and each of the previous fiscal years. The model's Sales table has the following three partitions:  
  
|Partition|Data from|  
|---------------|---------------|  
|Sales2020|Current fiscal year|  
|Sales2019-2010|Fiscal years 2010, 2011, 2012, 2013, 2014, 2015. 2016, 2017, 2018, 2019|  
|SalesOld|All fiscal years prior to the last ten years.|  
  
As new sales data is added for the current 2020 fiscal year; that data must be processed daily to be reflected accurately in the current fiscal year sales data analysis, therefore the Sales2020 partition is processed nightly.  
  
There's no need to process data in the Sales2019-2010 partition nightly. However, because sales data for the previous ten fiscal years can still occasionally change because of product returns and other adjustments, it must still be processed regularly, thus data in the Sales2019-2010 partition is processed monthly. Data in the SalesOld partition never changes, therefore only processed annually.  
  
When entering the 2021 fiscal year, a new Sales2021 partition is added to the model's Sales table. The Sales2020 partition can then be merged with the Sales2019-2010 partition and renamed to Sales2020-2011. Data from the 2010 fiscal year is eliminated from the Sales2020-2011 partition and moved into the SalesOld partition. All partitions are then processed to reflect changes.  

### Granularity

Using the Sales table example above, Yearly, monthly and daily partition granularity can be configured. Choice of granularity is influenced by various factors including how much data is required to be incrementally refreshed within an acceptable amount of processing time. For example, if only the last 3 days need to be refreshed daily, it may be beneficial to use daily granularity. 

Mixed granularity can be configured for scenarios such as near-real time refresh at low grain coupled with historical, static partitions at higher granularity. This results in fewer partitions, but also increases management overhead to ensure partition ranges are defined correctly.

Each scenario is unique. Be sure to define a granularity for your data model that most effectively uses memory and processing resources during refresh operations.

### Partitions in the model workspace database

When authoring tabular models in Visual Studio, you create new partitions, edit, merge, or delete partitions by using Partition Manager. Depending on the compatibility level of the model you are authoring, Partition Manager provides two modes for selecting tables, rows, and columns for a partition: For tabular 1400 and higher models with structured data sources, partitions are defined by using an Power Query M query. For provider data sources, partitions are defined by using an SQL query. For 1200 and lower models, a SQL query is defined.
  
### Partitions in a deployed model database

Partitions for a deployed model database appear as database objects in SSMS. You can create, edit, merge, and delete partitions for a deployed model by using the Partitions dialog box in SSMS or by script. To learn about managing partitions in SSMS, see [Create and manage tabular model partitions](../../analysis-services/tabular-models/create-and-manage-tabular-model-partitions.md).  

## Partitioning strategies

The [Automated Partition Management for Analysis Services Tabular Models](https://github.com/microsoft/Analysis-Services/blob/master/AsPartitionProcessing/Automated%20Partition%20Management%20for%20Analysis%20Services%20Tabular%20Models.pdf) whitepaper along with the accompanying [AsPartitionProcessing](https://github.com/microsoft/Analysis-Services/tree/master/AsPartitionProcessing) TOM code sample provided in GitHub. Concepts described in this whitepaper and project apply to all Analysis Services platforms.

### Automating partition management

By using a TMSL. A script executed by using the Invoke-ASCmd PowerShell cmdlet, with an Analysis Services Execute DDL Task in SQL Server Integration services (SSIS). 

## Limits on the number of partitions

Regardless of platform, there is no hard limit on the number of partition objects in a model. However, each partition has a memory footprint. An excessive number of partitions can consume valuable memory resources and the speed of metadata operations over too many partitions can adversely affect processing resources.

It's recommended you create the minimum number of partitions while still effectively meeting your partitioning goals. It's more important to focus an effective partitioning strategy based on granularity and  processing only those partitions with the most relevant changing data within available processing and memory resources. There is no guidance for an optimal number of partitions for a model. Every model is different. Available resources vary depending on your platform and plan.  

### Tabular Model Scripting Language (TMSL)

Partitions for a model are defined in the [Partitions object](../tmsl/partitions-object-tmsl.md). Actions on a partition object can be specified in [Create](create-command-tmsl.md), [CreateOrReplace](createorreplace-command-tmsl.md), [Alter](alter-command-tmsl.md), [Delete](delete-command-tmsl.md), [Refresh](refresh-command-tmsl.md), and [MergePartitions](mergepartitions-command-tmsl.md) commands. TMSL scripts can be executed in SQL Server Management Studio, by PowerShell, or by 

### Tabular Object Model (TOM)

## Process\refresh partitions

For deployed models, processing occurs by using SSMS, or by running a script which includes the process command and specifies processing options and settings. When authoring models by using Visual Studio, you can run process operations on the workspace database by using a Process command from the Model menu or toolbar. A Process operation can be specified for a partition, a table, or all.  
  
When a process operation is run, a connection to the data source is made using the data source connection. New data is imported into the model tables, relationships and hierarchies are rebuilt for each table, and calculations in calculated columns and measures are re-calculated.  
  
By further dividing a table into logical partitions, you can selectively determine what, when, and how the data in each partition is processed. When you deploy a model, processing of partitions can be completed manually using the Partitions dialog box in SSMS, or by using a script that executes a process command.  

Partitions can be processed independent of other partitions by using the **Partitions** dialog box in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] or by using a script. Processing has the following options:  
  
|Mode|Description|  
|----------|-----------------|  
|Process Default|Detects the process state of a partition object, and performs processing necessary to deliver unprocessed or partially processed partition objects to a fully processed state. Data for empty tables and partitions is loaded; hierarchies, calculated columns, and relationships are built or rebuilt.|  
|Process Full|Processes a partition object and all the objects that it contains. When Process Full is run for an object that has already been processed, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] drops all data in the object, and then processes the object. This kind of processing is required when a structural change has been made to an object.|  
|Process Data|Load data into a partition or a table without rebuilding hierarchies or relationships or recalculating calculated columns and measures.|  
|Process Clear|Removes all data from a partition.|  
|Process Add|Incrementally update partition with new data.|  

### Parallel processing

Analysis Services includes parallel processing for tables with two or more partitions, increasing processing performance. There are no configuration settings for parallel processing (see notes). Parallel processing occurs by default when you Process Table or you select multiple partitions for the same table and Process, however, you can still choose to process partitions independently or sequentially. To specify whether refresh operations run sequentially or in parallel, specify the **maxParallism** property option with the [Sequence command (TMSL)](https://docs.microsoft.com/analysis-services/tmsl/sequence-command-tmsl).

> [!NOTE]  
> If re-encoding is detected, parallel processing can cause increased use of system resources. This is because multiple partition operations need to be interrupted and restarted with the new encoding in-parallel.  
  
## Scripting

Tabular Object Model (TOM)

## See also

[Create Tables, Partitions, and Columns with the Tabular Object Model (TOM)](../tom/create-tables-partitions-and-columns-in-a-tabular-model.md)
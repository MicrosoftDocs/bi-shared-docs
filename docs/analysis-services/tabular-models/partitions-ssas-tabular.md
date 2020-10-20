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

  In tabular models, partitions divide a table into logical parts. Each partition can then be processed (refreshed) independent of other partitions. Partitions created by using the Partitions dialog box in Visual Studio during model authoring apply to the model workspace database. When the model is deployed, the partitions defined for the model workspace database are replicated in the deployed model database. You can further create and manage partitions for a deployed model database by using the Partitions dialog box in SQL Server Management Studio (SSMS) or by scripting with the Tabular Object Model (TOM) or Tabular Model Scripting Language (TMSL). Information provided in this article describes partitions created during model authoring by using the Partition Manager dialog box in Visual Studio. To learn more about creating and managing partitions for a deployed model, see [Create and manage tabular model partitions](../../analysis-services/tabular-models/create-and-manage-tabular-model-partitions-ssas-tabular.md).  
  
## Benefits

Partitions, in tabular models, divide a table into logical partition objects. Each partition can then be processed independent of other partitions. For example, a table may include certain row sets that contain data that rarely changes, but other row sets have data that changes often. In these cases, there is no need to process all of the data when you really just want to process a portion of the data. Partitions enable you to divide portions of data you need to process frequently from the data that can be processed less frequently.  

Effective model design utilizes partitions to eliminate unnecessary processing and subsequent processor load on Analysis Services servers, while at the same time, making certain that data is processed and refreshed often enough to reflect the most recent data from data sources. For example, a tabular model can have a Sales table which includes sales data for the current 2011 fiscal year and each of the previous fiscal years. The model's Sales table has the following three partitions:  
  
|Partition|Data from|  
|---------------|---------------|  
|Sales2020|Current fiscal year|  
|Sales2019-2010|Fiscal years 2010, 2011, 2012, 2013, 2014, 2015. 2016, 2017, 2018, 2019|  
|SalesOld|All fiscal years prior to the last ten years.|  
  
As new sales data is added for the current 2020 fiscal year; that data must be processed daily to accurately be reflected in current fiscal year sales data analysis, therefore the Sales2020 partition is processed nightly.  
  
There is no need to process data in the Sales2019-2010 partition nightly. However, because sales data for the previous ten fiscal years can still occasionally change because of product returns and other adjustments, it must still be processed regularly, thus data in the Sales2019-2010 partition is processed monthly. Data in the SalesOld partition never changes therefore only processed annually.  
  
When entering the 2021 fiscal year, a new Sales2021 partition is added to the model's Sales table. The Sales2020 partition can then be merged with the Sales2019-2010 partition and renamed to Sales2020-2011. Data from the 2010 fiscal year is eliminated from the Sales2020-2011 partition and moved into the SalesOld partition. All partitions are then processed to reflect changes.  
  
We've described a simple partitioning here. How you implement a partition strategy for your organization's tabular models will largely be dependent on your particular model data processing needs and available resources.  

### Partitions in the model workspace database

When authoring tabular models in Visual Studio, you create new partitions, edit, merge, or delete partitions by using the Partition Manager. Depending on the compatibility level of the model you are authoring, Partition Manager provides two modes for selecting tables, rows, and columns for a partition: For tabular 1400 and higher models, partitions are defined by using an Power Query M query, for 1200 and lower, a SQL query is defined.
  
### Partitions in a deployed model database

When you deploy a model, the partitions for the deployed model database will appear as database objects in SSMS. You can create, edit, merge, and delete partitions for a deployed model by using the Partitions dialog box in SSMS. Managing partitions for a deployed model in SSMS is outside the scope of this article. To learn about managing partitions in SSMS, see [Create and manage tabular model partitions](../../analysis-services/tabular-models/create-and-manage-tabular-model-partitions-ssas-tabular.md).  

## Permissions

 In order to create, manage, and process partitions in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], you must have the appropriate Analysis Services permissions defined in a security role. Each security role has one of the following permissions:  
  
|Permission|Actions|  
|----------------|-------------|  
|Administrator|Read, process, create, copy, merge, delete|  
|Process|Read, process|  
|Read Only|Read|  
  
## Processing (refresh) partitions

For deployed models, processing occurs by using SSMS, or by running a script which includes the process command and specifies processing options and settings. When authoring models by using Visual Studio, you can run process operations on the workspace database by using a Process command from the Model menu or toolbar. A Process operation can be specified for a partition, a table, or all.  
  
When a process operation is run, a connection to the data source is made using the data source connection. New data is imported into the model tables, relationships and hierarchies are rebuilt for each table, and calculations in calculated columns and measures are re-calculated.  
  
By further dividing a table into logical partitions, you can selectively determine what, when, and how the data in each partition is processed. When you deploy a model, processing of partitions can be completed manually using the Partitions dialog box in SSMS, or by using a script that executes a process command.  

Partitions can be processed (refreshed) independent of other partitions by using the **Partitions** dialog box in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] or by using a script. Processing has the following options:  
  
|Mode|Description|  
|----------|-----------------|  
|Process Default|Detects the process state of a partition object, and performs processing necessary to deliver unprocessed or partially processed partition objects to a fully processed state. Data for empty tables and partitions is loaded; hierarchies, calculated columns, and relationships are built or rebuilt.|  
|Process Full|Processes a partition object and all the objects that it contains. When Process Full is run for an object that has already been processed, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] drops all data in the object, and then processes the object. This kind of processing is required when a structural change has been made to an object.|  
|Process Data|Load data into a partition or a table without rebuilding hierarchies or relationships or recalculating calculated columns and measures.|  
|Process Clear|Removes all data from a partition.|  
|Process Add|Incrementally update partition with new data.|  

### Parallel processing

Analysis Services includes parallel processing for tables with two or more partitions, increasing processing performance. There are no configuration settings for parallel processing (see notes). Parallel processing occurs by default when you Process Table or you select multiple partitions for the same table and Process. You can still choose to process a tables partitions independently.  
  
To specify whether refresh operations run sequentially or in parallel, you can use the **maxParallism** property option with the [Sequence command (TMSL)](https://docs.microsoft.com/analysis-services/tmsl/sequence-command-tmsl).

> [!NOTE]  
>  If re-encoding is detected, parallel processing can cause increased use of system resources. This is because multiple partition operations need to be interrupted and restarted with the new encoding in-parallel.  
  

## See also

[Create and manage partitions in the workspace database](../../analysis-services/tabular-models/create-and-manage-partitions-in-the-workspace-database-ssas-tabular.md)  
[Process partitions in the workspace database](../../analysis-services/tabular-models/process-partitions-in-the-workspace-database-ssas-tabular.md)

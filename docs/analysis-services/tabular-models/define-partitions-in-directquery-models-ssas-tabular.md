---
title: "Define partitions in Analysis Services DirectQuery models | Microsoft Docs"
description: Describes how to define table partitions for DirectQuery models.
ms.date: 08/27/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Define partitions in DirectQuery models

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

This article describes how partitions are used in DirectQuery models. For more general information about partitions in tabular models, see [Partitions in tabular models](../../analysis-services/tabular-models/partitions-ssas-tabular.md).  
  
> [!NOTE]  
> While a table can have multiple partitions, in DirectQuery mode, only one of them can be designated for use in query execution. The single partition requirement applies to DirectQuery models at all compatibility levels.  
  
## Using partitions in DirectQuery mode

For each table, you must specify a single partition to use as the DirectQuery data source.  If there are multiple partitions, when you switch the model to enable DirectQuery mode, by default the first partition that was created in the table is flagged as the DirectQuery partition. You can change this later by using the Partition Manager in Tabular model designer in Visual Studio.  
  
Why allow only a single partition in DirectQuery mode? In tabular models (as in OLAP models), the partitions of a table are defined by PowerQuery M queries or SQL queries. The developer who creates the partition definition is responsible for ensuring that partitions do not overlap. Analysis Services does not check whether records belong in one or multiple partitions.  
  
Partitions in a cached tabular model behave the same way. If you are using an in-memory model, while the cache is being accessed, DAX formulas are evaluated for each partition, and the results are combined. However, when a tabular model uses DirectQuery mode, it would be impossible to evaluate multiple partitions, combine the results, and convert that into a SQL statement for sending to the relational data store. Doing so could lead to unacceptable loss of performance, as well as potential inaccuracies as the results are aggregated.  
  
Therefore, for queries answered in DirectQuery mode, the server uses a single partition that has been marked as the primary partition for DirectQuery access, called the *DirectQuery partition*.  The SQL query specified in the definition of this partition defines the complete set of data that can be used to answer queries in DirectQuery mode.  
  
If you do not explicitly define a partition, the engine simply issues a SQL query to the entire relational data source, performs any set-based operations dictated by the DAX formula, and returns the query results.  

## Change a DirectQuery partition

Because only one partition in a table can be designated as the DirectQuery partition, by default, Analysis Services uses the first partition that was created in the table. During model project authoring, you can change the DirectQuery partition by using Partition Manager. For deployed models, you can change the DirectQuery partition by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].  
  
### Change the DirectQuery partition for a tabular model project  
  
1. In Visual Studio, in the model designer, click on the table (tab) that contains the partitioned table.  
  
2. Click **Extensions** > **Table** > **Partitions**.  
  
3. In **Partition Manager**, the partition that is the current Direct Query partition in indicated by the prefix **(DirectQuery)** on the partition name.  
  
   Select a different partition from the **Partitions** list, and then click **Set as DirectQuery**. The **Set as DirectQuery** button is not enabled when the current DirectQuery partition is selected, and is not visible if the model has not been enabled for Direct Query mode.  
  
### Change the DirectQuery partition for a deployed tabular model  
  
1. In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open the model database in Object Explorer.  
  
2. Expand the **Tables** node, then right-click the partitioned table, and then select **Partitions**.  
  
     The partition that is designated for use with DirectQuery mode has the prefix (DirectQuery) on the partition name.  
  
3. To change to a different partition, click the **Direct Query** toolbar icon to open the **Set DirectQuery Partition** dialog box. The DirectQuery toolbar icon is not available on models that have not been enabled for Direct Query.  
  
4. Choose a different partition from the **Partition Name** dropdown list, and then change processing options on the partition if necessary.  

## See also

[Partitions](../../analysis-services/tabular-models/partitions-ssas-tabular.md)  

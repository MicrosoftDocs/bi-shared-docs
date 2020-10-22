---
title: "Create and manage partitions in the Analysis Services workspace database | Microsoft Docs"
description: Learn how to create and manage partitions in the model workspace database by using the Partition Manager dialog box in SQL Server Data Tools.
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
# Create and manage partitions in a model project

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

By default, each table in a tabular model has one partition. Tasks in this article describe how to create and manage partitions in the model project's workspace database by using the **Partition Manager** dialog box in Visual Studio. After a model has been deployed to a server (Azure Analysis Services, SSAS, Power BI), administrators can create and manage partitions in the (deployed) model by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or by script.
  
> [!NOTE]  
> Partitions in the model workspace database cannot be merged by using Partition Manager. Partitions can be merged only by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or by script.  
  
## Tasks

To create and manage partitions, use the **Partitions Manager** dialog box. To view the **Partitions Manager** dialog box, click **Extensions** > **Table** > **Partitions**.  
  
### To create a new partition  
  
1. In the model designer, select the table for which you want to define a partition.  
  
2. Click on the **Table** menu, and then click **Partitions**.  
  
3. In **Partition Manager**, in the **Table** listbox, verify or select the table you want to partition, and then click **New**.  
  
4. In **Partition Name**, type a name for the partition. By default, the name of the default partition will be incrementally numbered for each new partition.  
  
5. You can select the rows and columns to be included in the partition by using Table Preview mode or by using a SQL query created using Query Editor mode.  
  
     To use Table Preview mode (default), click the **Table Preview** button near the upper-right corner of the preview window. Select the columns you want to include in the partition by selecting the checkbox next to the column name. To filter rows, right click a cell value, and click **Filter by Selected Cell Value**.  
  
     To use a SQL statement, click the **Query Editor** button near the upper-right corner of the preview window, then type or paste a SQL query statement into the query window. To validate your statement, click **Validate**. To use the Query Designer, click **Design**.  
  
### To copy a partition  
  
1. In **Partition Manager**, in the **Table** listbox, verify or select the table that contains the partition you want to copy.  
  
2. In the **Partitions** list, select the partition you want to copy and then click **Copy**.  
  
3. In **Partition Name**, type a new name for the partition.  
  
### To delete a partition  
  
1. In **Partition Manager**, in the **Table** listbox, verify or select the table that contains the partition you want to delete.  
  
2. In the **Partitions** list, select the partition you want to delete and then click **Delete**.  

## See also

[Create and manage tabular model partitions](../../analysis-services/tabular-models/create-and-manage-tabular-model-partitions.md)
---
title: "Create and Manage Tabular Model Partitions | Microsoft Docs"
description: Learn how to create and manage partitions for a deployed model. 
ms.date: 10/22/2020
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: how-to
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Create and manage tabular model partitions

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

Partitions divide a table into logical parts. Each partition can then be processed (Refreshed) independent of other partitions. Partitions defined for a model during model authoring are duplicated in a deployed model. Once deployed, you can manage those partitions by using the **Partitions** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)](SSMS), by using Tabular Model Scripting Language (TMSL), or programmatically with the Tabular Object Model (TOM).

## Model project in Visual Studio

By default, each table in a tabular model has one partition. Tasks in this section describe how to create and manage partitions in the model project's *workspace database* by using Partition Manager. After a model has been deployed (Azure Analysis Services, SSAS, Power BI), model database administrators can create and manage partitions in the deployed model by using SSMS or by script.

Partitions in the model workspace database cannot be merged by using Partition Manager. Partitions can be merged only by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or by script.  

To create and manage partitions in Visual Studio, use Partition Manager. To view the Partitions Manager dialog box, click **Extensions** > **Table** > **Partitions**, or in **Tabular Model Explorer**, right-click a table, and then click **Partitions**.
  
#### To create a new partition
  
1. In **Partition Manager**, in the **Table** listbox, verify or select the table you want to partition, and then click **New**.  
  
1. In **Partition Name**, type a name for the partition. By default, the name of the table is specified and will be incrementally numbered for each new partition.  
  
1. In **Query Expression** edit or specify a new Power Query M expression, or click **Design** to open Power Query Editor where you can select and filter data to be included in the partition. For legacy (provider) data sources, specify a SQL statement, or click **Design** to open (SQL) Query Editor.

    **Important:** When creating a new partition or copying an existing partition, make sure the new partition query expression defines a unique portion of data, preventing replicated data in two or more partitions.

1. Click **Validate**.
  
#### To copy a partition  
  
1. In **Partition Manager**, in the **Table** listbox, verify or select the table that contains the partition you want to copy.  
  
1. In the **Partitions** list, select the partition you want to copy and then click **Copy**.  
  
1. In **Partition Name**, type a new name for the partition.

1. In **Query Expression** edit or specify a new Power Query M expression, or click **Design** to open Power Query Editor where you can select and filter data to be included in the partition.
1. Click **Validate**.

## Deployed model by using SSMS

To create and manage partitions for a deployed tabular model database, use the Partitions dialog box in SSMS. To open the Partitions dialog box, in SSMS, right-click a table, and then click **Partitions**.  
  
#### To create a new partition
  
1. In the **Partitions** dialog box, click **New**.  
  
1. In **Partition Name**, type a name for the partition. By default, the name of the default partition will be incrementally numbered for each new partition.  
  
1. In **Query Statement**, type or paste a Power Query M or SQL query statement that defines the columns and any clauses you want to include.
  
1. Click **Check Syntax** to validate.  
  
#### To copy a partition
  
1. In the **Partitions** dialog box, in the **Partitions** list, select the partition you want to copy, and then click **Copy**.  
  
1. In **Partition Name**, type a new name for the partition.  
  
1. In **Query Statement**, edit the query statement.
  
#### To merge two or more partitions  
  
- In the **Partitions** dialog box, in the **Partitions** list, use Ctrl+click to select the partitions you want to merge, and then click **Merge**.  
  
> [!IMPORTANT]  
> Merging partitions does not update the partition metadata. You must edit the Power Query M or SQL query expression for the resulting partition to make sure processing operations process all data in the *merged* partition.  

## Deployed model by using script

Partitions are defined by the [Partitions object](../tmsl/partitions-object-tmsl.md) in Tabular Model Scripting Language (TMSL). To create, copy, or delete partitions, execute a [CreaterOrReplace](../tmsl/createorreplace-command-tmsl.md), [Create](../tmsl/create-command-tmsl.md), [Alter](../tmsl/alter-command-tmsl.md), or [Delete](../tmsl/delete-command-tmsl.md) command. To merge partitions, execute a [MergePartitions](../tmsl/mergepartitions-command-tmsl.md) command.

To learn more about executing a TMSL script by using SSMS or PowerShell, see [How to use TMSL](../tmsl/tabular-model-scripting-language-tmsl-reference.md#how-to-use-tmsl).

## Programmatically by using TOM

Partitions are represented by a Partition class in Microsoft.AnalysisServices.Tabular namespace. To learn more, see [Create Tables, Partitions, and Columns (TOM)](../tom/create-tables-partitions-and-columns-in-a-tabular-model.md).


## See also  

[Process database, table, or partition](process-database-table-or-partition-analysis-services.md)  
[Partitions in tabular models](partitions-ssas-tabular.md)
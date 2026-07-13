---
title: "Enable Dimension Writeback | Microsoft Docs"
description: Add the dimension writeback enhancement to a cube or dimension to allow users to manually modify the dimension structure and members.
ms.date: 05/02/2018
ms.service: azure-analysis-services
ms.custom: multidimensional-models
ms.topic: how-to

---
# BI Wizard - Enable dimension writeback
[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]
  Add the dimension writeback enhancement to a cube or dimension to allow users to manually modify the dimension structure and members. Updates to a write-enabled dimension are recorded directly in the dimension table. This enhancement changes the **WriteEnabled** property setting for a dimension.  
  
 To add dimension writeback, use the Business Intelligence Wizard, and select the **Enable dimension writeback** option on the **Choose Enhancement** page. This wizard then guides you through the steps of selecting a dimension to which you want to apply dimension writeback and setting this option for the selected dimension.  
  
> [!NOTE]  
>  Writeback is supported for SQL Server relational databases and data marts only.  
  
## Select a dimension  
 On the first **Enable Dimension Writeback** page of the wizard, specify the dimension to which you want to apply dimension writeback. When you add the dimension writeback enhancement to this selected dimension, you change the dimension. All cubes that include the selected dimension inherit these changes.  
  
## Set dimension writeback capability  
 On the second **Enable Dimension Writeback** page of the wizard, set the **Enable writeback in the dimension** option. Selecting this option automatically sets the **WriteEnabled** property of the dimension to **True**. Clearing this option automatically sets the property to **False**.  
  
## Remarks  
 When you create a new member, you must include every attribute in a dimension. You can't insert a member without specifying a value for the key attribute of the dimension. Therefore, creating members is subject to any constraints, such as non-null key values, that are defined on the dimension table. Consider columns optionally specified by dimension properties, such as columns specified in the **CustomRollupColumn**, **CustomRollupPropertiesColumn**, or the **UnaryOperatorColumn** dimension properties.  
  
> [!IMPORTANT]  
>  If you use SQL Azure as a data source to perform writeback into an Analysis Services database, the operation fails. This failure is by design, because the provider option that enables multiple active result sets (MARS) isn't turned on by default.  
>   
>  The workaround is to add the following setting in the connection string, to support MARS and to enable writeback:  
>   
>  `"MultipleActiveResultSets=True"`  
>   
>  For more information, see [Using Multiple Active Result Sets &#40;MARS&#41;](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars).
  
## See also  
 [Write-Enabled Dimensions](../../analysis-services/multidimensional-models-olap-logical-dimension-objects/write-enabled-dimensions.md)  
  
  

---
title: "Set Custom Member Formulas for Attributes in a Dimension | Microsoft Docs"
description: Add a custom member formula to a cube or dimension to replace the default aggregation that is associated with a dimension member.
ms.date: 05/02/2018
ms.service: analysis-services
ms.custom: multidimensional-models
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# BI Wizard - Custom Member Formulas for Attributes in a Dimension
[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]
  Add a custom member formula enhancement to a cube or dimension to replace the default aggregation that is associated with a dimension member with the results of a Multidimensional Expressions (MDX) expression. (This enhancement sets the **CustomRollupColumn** property on a specified attribute in a dimension.)  
  
> [!NOTE]  
>  A custom member formula is available only for dimensions that are based on existing data sources. For dimensions that were created without using a data source, you must run the Schema Generation Wizard to create a data source view before adding a custom member formula.  
  
 To add a custom member formula, you use the Business Intelligence Wizard, and select the **Create a custom member formula** option on the **Choose Enhancement** page. This wizard then guides you through the steps of selecting a dimension to which you want to apply a custom member formula and enabling the custom member formula.  
  
## Selecting a Dimension  
 On the first **Create a Custom Member Formula** page of the wizard, you specify the dimension to which you want to apply a custom member formula. The custom member formula enhancement added to this selected dimension will result in changes to the dimension. These changes will be inherited by all cubes that include the selected dimension.  
  
## Enabling a Custom Member Formula  
 On the second **Create a Custom Member Formula** page, you associate the source column that contains the custom member formula with one or more attributes in the dimension. In the **Attribute** column, select the check box next to the attribute that you want to associate with the custom member formula column. After you select each attribute, the wizard displays the **Select a Column** dialog box. In this dialog box, click the column in the dimension table that contains the formula. If you want to change a selection after you close the **Select a Column** dialog box, click the **Source Column** cell that you want to change, and then click the ellipsis (**...**) to open the **Select a Column** dialog box again.  
  
## See Also  
 [Use the Business Intelligence Wizard to Enhance Dimensions](./bi-wizard-add-account-intelligence-to-a-dimension.md?viewFallbackFrom=sql-server-ver15)  
  

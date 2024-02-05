---
title: "Create a Finance Account of parent-child type Dimension | Microsoft Docs"
description: Learn about the account type dimension, whose attributes represent a chart of accounts for financial reporting purposes.
ms.date: 05/02/2018
ms.service: analysis-services
ms.custom: multidimensional-models
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Database Dimensions - Finance Account of parent-child type
[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]
  In [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], an account type dimension is a dimension whose attributes represent a chart of accounts for financial reporting purposes.  
  
 An account dimension lets you selectively manage aggregation behavior across accounts over time. An account dimension also lets use a standard mechanism to resolve most of the nonstandard aggregation issues typically encountered in business intelligence solutions that handle financial data. If you did not have such a standard mechanism, resolving these nonstandard aggregation issues would require custom rollup formulas, calculated members, or Multidimensional Expressions (MDX) scripts.  
  
 To identify a dimension as an account dimension, set the **Type** property of the dimension to **Accounts**.  
  
## Dimension Structure  
 An account dimension contains, at least, two attributes:  
  
-   A key attribute-an attribute that identifies individual accounts in the dimension table for the account dimension.  
  
-   An account attribute-a parent attribute that describes how accounts are hierarchically arranged in the account dimension.  
  
     To identify an attribute as an account attribute, set the **Type** property of the attribute to **Account** and the **Usage** property to **Parent**.  
  
 Account dimensions can optionally contain the following attributes:  
  
-   An account type attribute-an attribute that defines the account type for each account in the dimension. The member names of the account type attribute map to the account types defined for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database or project, and indicate the aggregation function used by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] for those accounts. You can also use unary operators or custom rollup formulas to determine aggregation behavior for account attributes, but account types let you to easily apply consistent behavior to a chart of accounts without requiring changes to the underlying relational database.  
  
     To identify an account type attribute, set the **Type** property of the attribute to **AccountType**.  
  
-   An account name attribute-an attribute that is used for reporting purposes. You identify an account name attribute by setting the **Type** property of the attribute to **AccountName**.  
  
-   An account number attribute-an attribute that is used for reporting purposes. You identify an account number attribute by setting the **Type** property of the attribute to **AccountNumber**.  
  
 For more information about attribute types, see [Configure Attribute Types](../../analysis-services/multidimensional-models/attribute-properties-configure-attribute-types.md).  
  
## Adding Account Intelligence with the Business Intelligence Wizard  
 After you have defined an account dimension and added that dimension to a cube, you can use the Business Intelligence Wizard to adding account intelligence functionality, such as identifying and mapping account types, to the dimension. For more information, see [Add Account Intelligence to a Dimension](../../analysis-services/multidimensional-models/bi-wizard-add-account-intelligence-to-a-dimension.md).  
  
## See Also  
 [Attributes and Attribute Hierarchies](../../analysis-services/multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md)   
 [Business Intelligence Wizard F1 Help](../analysis-services-overview.md?viewFallbackFrom=sql-server-ver15)   
 [Dimension Types](../../analysis-services/multidimensional-models-olap-logical-dimension-objects/database-dimension-properties-types.md)  
  

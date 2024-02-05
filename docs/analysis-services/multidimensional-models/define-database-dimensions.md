---
title: "Define Database Dimensions | Microsoft Docs"
description: Use Dimension Designer in SQL Server Data Tools to configure an existing database dimension in a Microsoft SQL Server Analysis Services project or database.
ms.date: 05/02/2018
ms.service: analysis-services
ms.custom: multidimensional-models
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Define Database Dimensions
[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]
  Use Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to configure an existing database dimension in a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or database. You can use Dimension Designer to do the following:  
  
-   Configure the dimension-level properties.  
  
-   Add and configure dimension attributes.  
  
-   Define and configure user-defined hierarchies.  
  
-   Define and configure relationships between attributes.  
  
-   Define dimension translations.  
  
-   For processed dimensions, you can browse the dimension structure and view data.  
  
 After you modify a dimension, attribute, or hierarchy, you must process that dimension to view the changes. When working in project mode, you deploy the changes to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance before processing.  
  
 For more information about how to open a dimension in Dimension Designer, see [Modify or Delete a Database Dimension in Solution Explorer](../../analysis-services/multidimensional-models/database-dimensions-modify-or-delete-a-database-dimension-in-solution-explorer.md).  
  
 Dimension Designer has three different tabs, which are described in the following table.  
  
|Tab|Description|  
|---------|-----------------|  
|**Dimension Structure**|Use this tab to work with the structure of a dimension-to examine or create the data source view schema for a dimension, to work with attributes, and to organize attributes in user-defined hierarchies.|  
|**Attribute Relationships**|Use this tab to create, modify, or delete the attribute relationships of a dimension.|  
|**Translations**|Use this tab to add and edit translations of dimension metadata in different languages.|  
|**Browser**|Use this tab to examine the members of a processed dimension and to review translations of dimension metadata.|  
  
 The following topics describe the tasks that you can perform in Dimension Designer.  
  
 [Dimension Attribute Properties Reference](../../analysis-services/multidimensional-models/dimension-attribute-properties-reference.md)  
 Describes how to define and configure a dimension attribute.  
  
 [Create User-Defined Hierarchies](../../analysis-services/multidimensional-models/user-defined-hierarchies-create.md)  
 Describes how to define and configure a user-defined hierarchy.  
  
 [Define Attribute Relationships](../../analysis-services/multidimensional-models/attribute-relationships-define.md)  
 Describes how to define and configure an attribute relationship.  
  
 [Use the Business Intelligence Wizard to Enhance Dimensions](./bi-wizard-add-account-intelligence-to-a-dimension.md?viewFallbackFrom=sql-server-ver15)  
 Describes how to use the Business Intelligence Wizard to enhance a dimension.  
  

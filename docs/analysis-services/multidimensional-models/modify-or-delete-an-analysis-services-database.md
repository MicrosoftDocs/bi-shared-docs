---
title: "Modify or Delete an Analysis Services Database | Microsoft Docs"
description: Modify or delete an Analysis Services database before deployment in SQL Server Data Tools and after deployment in SQL Server Management Studio.
ms.date: 05/02/2018
ms.service: analysis-services
ms.custom: multidimensional-models
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Modify or Delete an Analysis Services Database
[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]
  You can change the name and description of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database before deployment in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and after deployment in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]. You can also adjust additional settings on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, depending on the environment.  
  
> [!NOTE]  
>  You cannot change database properties using [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] in online mode.  
  
## Modifying Databases Using SQL Server Management Studio  
 Once an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database is deployed, you can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to change the impersonation mode used by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] when connecting to data sources contained by the database. The impersonation mode allows you to specify the security context used by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] when attempting to connect to a data source for processing, browsing, or drillthrough purposes.  
  
## Modifying Databases Using SQL Server Data Tools  
 You can use [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] in project mode to modify the translations for the caption and description of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project used to define a database. For more information about using translations in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, see [Globalization scenarios for Analysis Services](../../analysis-services/globalization-scenarios-for-analysis-services.md).  
  
 You can also set the aliases and aggregation functions associated with account types used by account attributes in dimensions contained by the database. Aliases allow you to select the business-specific terminology used by your organization for the account types in a chart of accounts. The account types are used by members of an account attribute to indicate how to aggregate measures over each member by using the aggregation functions specified for each account type contained in the database. For more information about account attributes, see [Attributes and Attribute Hierarchies](../../analysis-services/multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md).  
  
## Deleting Databases  
 Deleting an existing [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database deletes the database and all cubes, dimensions, and mining models in the database. You can only delete an existing [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].  
  
#### To delete an Analysis Services database  
  
1.  Connect to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.  
  
2.  In **Object Explorer**, expand the node for the connected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance and ensure that the object to be deleted is visible.  
  
3.  Right-click the object to be deleted and select **Delete**.  
  
4.  In the **Delete Object** dialog box, click **OK**.  
  
## See Also  
 [Document and Script an Analysis Services Database](../../analysis-services/multidimensional-models/document-and-script-an-analysis-services-database.md)  
  
  

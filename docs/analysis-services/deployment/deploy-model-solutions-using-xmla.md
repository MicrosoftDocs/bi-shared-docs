---
title: "Deploy Analysis Services solutions by using XMLA | Microsoft Docs"
description: Learn how to deploy SQL Server Analysis Services solutions as a script of a database or one of its objects by using XMLA.
ms.date: 05/02/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom:
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Deploy model solutions by using XMLA

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

  In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], the **CREATE To** option of the **Script Database As** command creates an XML script of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database or one of its constituent objects. The resulting script can then be run to recreate the schema (metadata) of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database. The script generates the entire database, and there is no mechanism for incrementally updating already deployed objects when using the script. After running the script and deploying the database, the newly created database must be processed before users can browse it.  
  
 For more information about the **Script Database As** command, see [Document and script an Analysis Services database](../../analysis-services/multidimensional-models/document-and-script-an-analysis-services-database.md).  
  
## Modifying object properties in the XML script

 When using the **Script Database As** command, you cannot modify specific properties (such as the database name, data source connection strings, and security settings) of the database objects. These properties must either be manually modified in the script after the script has been generated or modified in the deployed database after running the script.  
  
> [!IMPORTANT]  
>  The XML script will not contain the password if this is specified in either the connection string for a data source or for impersonation purposes. Since the password is required for processing purposes in this scenario, you will either need to add this manually to the XML script before it executes or add it after the XML script executes.  
  
## See also

 [Deploy model solutions by using the Deployment Wizard](../../analysis-services/deployment/deploy-model-solutions-using-the-deployment-wizard.md)   
 [Synchronize Analysis Services databases](../../analysis-services/multidimensional-models/synchronize-analysis-services-databases.md)  
  
  

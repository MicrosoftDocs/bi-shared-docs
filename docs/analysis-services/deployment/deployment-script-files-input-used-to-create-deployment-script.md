---
title: "Understanding the Input Files Used to Create the Deployment Script | Microsoft Docs"
description: Learn about the input files used to create a deployment script in SQL Server Analysis Services and about modifying input files.
ms.date: 05/02/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: multidimensional-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Deployment Script Files - Input Used to Create Deployment Script
[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

  When you build a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] generates files for the project. [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] puts these files in the Output folder of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project. By default output is out in the \Bin folder. The following table lists the XML files that [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] creates.  
  
|File|Description|  
|---------------|-----------------|  
|\<*project name*>.asdatabase|An XMLA file for Multidimensional or 1100/1103 Tabular model projects, or a JSON file for Tabular 1200 and higher model projects. Contains the declarative definitions for all the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects in the project.|  
|\<*project name*>.deploymenttargets|Contains the name of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance and database in which the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects will be created.|  
|\<*project name*>.configsettings|Contains environment specific settings, such as data source connection information and object storage locations. Settings in this file override settings in the \<*project name*>.asdatabase file.|  
|\<*project name*>.deploymentoptions|Contains deployment options, such as whether deployment is transactional and whether deployed objects should be processed after deployment.|  
  
> [!NOTE]  
>  [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] never stores passwords in its project files.  
  
## Modifying the Input Files  
 Modifying the values in the input files, or the values retrieved from the input files, makes it possible to change the deployment destination, the configuration settings, and deployment options without editing the whole \<*project name*>.asdatabase file (or a whole script file if you generate a script from an existing [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database). Being able to modify individual files lets you easily create different deployment scripts for different purposes.  
  
 The following topics explain how to modify values in the various input files:  
  
-   [Specifying the Installation Target](../../analysis-services/deployment/deployment-script-files-specifying-the-installation-target.md)  
  
-   [Specifying Partition and Role Deployment Options](../../analysis-services/deployment/deployment-script-files-partition-and-role-deployment-options.md)  
  
-   [Specifying Configuration Settings for Solution Deployment](../../analysis-services/deployment/deployment-script-files-solution-deployment-config-settings.md)  
  
-   [Specifying Processing Options](../../analysis-services/deployment/deployment-script-files-specifying-processing-options.md)  
  
## See Also  
 [Running the Analysis Services Deployment Wizard](../../analysis-services/deployment/running-the-analysis-services-deployment-wizard.md)   
 [Understanding the Analysis Services Deployment Script](../../analysis-services/deployment/understanding-the-analysis-services-deployment-script.md)  
  
  

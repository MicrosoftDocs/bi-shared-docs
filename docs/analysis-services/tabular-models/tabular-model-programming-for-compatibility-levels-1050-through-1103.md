---
title: "Analysis Services tabular model programming for levels 1050 - 1103 | Microsoft Docs"
description: Learn how tabular models use relational constructs to model Analysis Services data in compatibility levels 1050 and 1103.
ms.date: 12/07/2020
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan
monikerRange: "asallproducts-allversions || >= sql-analysis-services-2016"
---
# Tabular model programming for compatibility levels 1050 and 1103

[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]

  Tabular models use relational constructs to model the Analysis Services data used by analytical and reporting applications. These models run on an Analysis Service instance that is configured for tabular mode, using an in-memory analytics engine for storage and fast table scans that aggregate and calculate data as it is requested.  
  
 If the requirements of your custom BI solution are best met by a tabular model database, you can use any of the Analysis Services client libraries and programming interfaces to integrate your application with tabular models on an Analysis Services instance. To query and calculate tabular model data, you can use either embedded MDX or DAX in your code.  
  
 For Tabular models created in earlier versions of Analysis Services, in particular models at compatibility levels 1050 through 1103, the objects you work with programmatically in AMO, ADOMD.NET, XMLA, or OLE DB are fundamentally the same for both tabular and multidimensional solutions. Specifically, the object metadata defined for multidimensional models is also used for tabular model compatibility levels 1050-1103.  
  
 Beginning with SQL Server 2016, Tabular models can be built or upgraded to the 1200 or higher compatibility level, which uses tabular metadata to define the model. Metadata and programmability are fundamentally different at this level. See [Tabular Model Programming for Compatibility Level 1200 and higher](./tabular-model-programming-for-compatibility-level-1200.md) and [Upgrade Analysis Services](/sql/database-engine/install-windows/upgrade-analysis-services) for more information.
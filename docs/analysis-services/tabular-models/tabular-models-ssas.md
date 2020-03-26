---
title: "Tabular modeling overview - Analysis Services  | Microsoft Docs"
ms.date: 01/29/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Tabular modeling overview

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

  Tabular models in Analysis Services are databases that run in-memory or in DirectQuery mode, connecting to data directly from back-end relational data sources. By using state-of-the-art compression algorithms and multi-threaded query processor, the Analysis Services Vertipaq analytics engine delivers fast access to tabular model objects and data by reporting client applications like Power BI and Excel.  
  
 While in-memory models are the default, DirectQuery is an alternative query mode for models that are either too large to fit in memory, or when data volatility precludes a reasonable processing strategy. DirectQuery achieves parity with in-memory models through support for a wide array of data sources, ability to handle calculated tables and columns in a DirectQuery model, row level security via DAX expressions that reach the back-end database, and query optimizations that result in faster throughput.
  
 Tabular models are created in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] using the Tabular model project template. The project template provides a design surface for creating semantic model objects like tables, partitions, relationships, hierarchies, measures, and KPIs. 
  
 Tabular models can be deployed to Azure Analysis Services or an instance of SQL Server Analysis Services configured for Tabular server mode. Deployed tabular models can be managed in SQL Server Management Studio. 


  

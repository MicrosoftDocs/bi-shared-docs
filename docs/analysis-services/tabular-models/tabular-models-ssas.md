---
title: "Tabular modeling overview - Analysis Services  | Microsoft Docs"
description: Learn how tabular models in Analysis Services are databases that run in-memory or in DirectQuery mode, connecting to data from back-end relational data sources.
ms.date: 06/08/2021
ms.service: analysis-services
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Tabular modeling overview

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

Tabular models in Analysis Services are databases that run in-memory or in DirectQuery mode, connecting to data from back-end relational data sources. By using state-of-the-art compression algorithms and multi-threaded query processor, the Analysis Services VertiPaq analytics engine delivers fast access to tabular model objects and data by reporting client applications like Power BI and Excel.  
  
While in-memory models are the default, DirectQuery is an alternative query mode for models that are either too large to fit in memory, or when data volatility precludes a reasonable processing strategy. DirectQuery achieves parity with in-memory models through support for a wide array of data sources, ability to handle calculated tables and columns in a DirectQuery model, row level security via DAX expressions that reach the back-end database, and query optimizations that result in faster throughput.
  
Tabular models are created in Microsoft Visual Studio with the Analysis Services projects extension. The extension installs a tabular model designer, which provides a design surface for creating semantic model objects like tables, partitions, relationships, hierarchies, measures, and KPIs.
  
Tabular models can be deployed to Power BI Premium, Azure Analysis Services, or an instance of SQL Server Analysis Services configured for Tabular server mode. Deployed tabular models can be managed in SQL Server Management Studio or by using many different tools.

## See also

[Comparing tabular and multidimensional solutions](../comparing-tabular-and-multidimensional-solutions-ssas.md)  
[Analysis Services in Power BI Premium](/power-bi/service-premium-what-is#analysis-services-in-power-bi-premium-preview)  
[Azure Analysis Services](/azure/analysis-services/)

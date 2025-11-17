---
title: "Analysis Services features supported by SQL Server edition | Microsoft Docs"
description: Learn about features supported by different editions of SQL Server 2016, 2017, 2019 Analysis Services.
ms.date: 06/09/2022
ms.service: analysis-services
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis
monikerRange: "asallproducts-allversions || >= sql-analysis-services-2016"
---
# Analysis Services features supported by SQL Server edition

[!INCLUDE[appliesto-sqlas](includes/appliesto-sqlas.md)]

This article describes features supported by different editions of SQL Server 2016, 2017, 2019, 2022, 2025 Analysis Services. Evaluation edition supports Enterprise edition features.

> [!IMPORTANT]
> SQL Server 2025 introduces the **Standard Developer** edition. SQL Server 2025 **Standard Developer** edition is a free edition licensed for development. It includes all features of SQL Server **Standard** edition. **Enterprise Developer** is functionally equivalent to the **Developer** edition in previous versions, and includes all of the features enabled for the SQL Server **Enterprise** edition.

## Analysis Services (servers)
  
|Feature|Enterprise|Standard|Web|Express with Advanced Services|Express with Tools|Express|Enterprise Developer|Standard Developer|  
|-|-|-|-|-|-|-|-|-|
|Scalable shared databases|Yes||||||Yes||
|Backup/Restore|Yes|Yes|||||Yes|Yes|
|Attach/Detach databases|Yes||||||Yes||
|Synchronize databases|Yes||||||Yes|  |
|Failover cluster instances|Yes<br /><br /> Number of nodes is the operating system maximum|Yes<br /><br /> Support for 2 nodes|||||Yes<br /><br /> Number of nodes is the operating system maximum|Yes<br /><br /> Support for 2 nodes|
|Programmability (AMO, ADOMD.Net, OLEDB, XML/A, ASSL, TMSL)|Yes|Yes|||||Yes|Yes|
  
## Tabular models
  
|Feature|Enterprise|Standard|Web|Express with Advanced Services|Express with Tools|Express|Enterprise Developer|Standard Developer|  
|-|-|-|-|-|-|-|-|-|
|Hierarchies|Yes|Yes|||||Yes|Yes|
|KPIs|Yes|Yes|||||Yes|Yes|
|Perspectives|Yes||||||Yes||
|Translations|Yes|Yes|||||Yes|Yes|
|DAX calculations, DAX queries, MDX queries|Yes|Yes|||||Yes|Yes|
|Row-level security|Yes|Yes|||||Yes|Yes|
|Multiple partitions|Yes||||||Yes||
|Calculation groups|Yes (beginning with SQL Server 2019)|Yes |||||Yes (beginning with SQL Server 2019)|Yes|
|Query interleaving|Yes (beginning with SQL Server 2019)|Yes (beginning with SQL Server 2019)|||||Yes (beginning with SQL Server 2019)|Yes|
|Many-to-many relationships|Yes (beginning with SQL Server 2019)|Yes (beginning with SQL Server 2019)|||||Yes (beginning with SQL Server 2019)|Yes|
|In-memory storage mode|Yes|Yes|||||Yes|Yes|
|DirectQuery mode|Yes|Yes (beginning with SQL Server 2019)|||||Yes|Yes|

## Multidimensional models
  
|Feature|Enterprise|Standard|Web|Express with Advanced Services|Express with Tools|Express|Enterprise Developer|Standard Developer|  
|-|-|-|-|-|-|-|-|-|
|Semi-additive measures|Yes|No <sup>[1](#sameas)</sup>|||||Yes|No|
|Hierarchies|Yes|Yes|||||Yes|Yes|
|KPIs|Yes|Yes|||||Yes|Yes|
|Perspectives|Yes||||||Yes||
|Actions|Yes|Yes|||||Yes|Yes|
|Account intelligence|Yes|Yes|||||Yes|Yes|
|Time intelligence|Yes|Yes|||||Yes|Yes|
|Custom rollups|Yes|Yes|||||Yes|Yes|
|Writeback cube|Yes|Yes|||||Yes|Yes|
|Writeback dimensions|Yes <sup>[2](#wb)</sup>||||||Yes <sup>[2](#wb)</sup>||
|Drillthrough|Yes|Yes|||||Yes|Yes|
|Advanced hierarchy types (parent-child and ragged hierarchies)|Yes|Yes|||||Yes|Yes|
|Advanced dimensions (reference dimensions, many-to-many dimensions)|Yes|Yes|||||Yes|Yes|
|Linked measures and dimensions|Yes|Yes  <sup>[3](#linkmd)</sup> |||||Yes|Yes  <sup>[3](#linkmd)</sup>|
|Translations|Yes|Yes|||||Yes|Yes|
|Aggregations|Yes|Yes|||||Yes|Yes|
|Multiple partitions|Yes|Yes, up to 3|||||Yes|Yes, up to 3|
|Proactive caching|Yes||||||Yes||
|Custom assemblies (stored procedures)|Yes|Yes|||||Yes|Yes|
|MDX queries and scripts|Yes|Yes|||||Yes|Yes|
|DAX queries|Yes|Yes|||||Yes|Yes|
|Role-based security model|Yes|Yes|||||Yes|Yes|
|Dimension and cell-level security|Yes|Yes|||||Yes|Yes|
|Scalable string storage|Yes|Yes|||||Yes|Yes|
|MOLAP, ROLAP, and HOLAP storage models|Yes|Yes|||||Yes|Yes|
|Binary and compressed XML transport|Yes|Yes|||||Yes|Yes|
|Push-mode processing|Yes||||||Yes||
|Measure expressions|Yes||||||Yes||
  
<a name="sameas">[1]</a> The LastChild semi-additive measure is supported in Standard edition, but other semi-additive measures, such as None, FirstChild, FirstNonEmpty, LastNonEmpty, AverageOfChildren, and ByAccount, are not. Additive measures, such as Sum, Count, Min, Max, and non-additive measures (DistinctCount) are supported on all editions. 

<a name="wb">[2]</a> Writeback dimensions are discontinued in SQL Server Analysis Services 2019 and later.
 
<a name="linkmd">[3]</a> Standard edition supports linking measures and dimensions within the same database, but not from other databases or instances.

::: moniker range="asallproducts-allversions || sql-analysis-services-2016 || sql-analysis-services-2017 || sql-analysis-services-2019"

## Power Pivot for SharePoint

> [!IMPORTANT]
> Power Pivot mode is **Discontinued** in SQL Server Analysis Services 2022. To learn more, see [What's new in SQL Server 2022 Analysis Services - Discontinued features](what-s-new-in-sql-server-analysis-services.md?view=sql-analysis-services-2022&preserve-view=true#discontinued-features-in-ssas-2022).

|Feature|Enterprise|Standard|Web|Express with Advanced Services|Express with Tools|Express|Enterprise Developer|Standard Developer|  
|-|-|-|-|-|-|-|-|-| 
|SharePoint farm integration based on shared service architecture|Yes||||||Yes|  
|Usage reporting|Yes||||||Yes||
|Health monitoring rules|Yes||||||Yes||
|Power Pivot gallery|Yes||||||Yes||
|Power Pivot data refresh|Yes||||||Yes||
|Power Pivot data feeds|Yes||||||Yes||

## Data Mining  

> [!IMPORTANT]
> Data mining is **Discontinued** in SQL Server Analysis Services 2022. To learn more, see [What's new in SQL Server 2022 Analysis Services - Discontinued features](what-s-new-in-sql-server-analysis-services.md?view=sql-analysis-services-2022&preserve-view=true#discontinued-features-in-ssas-2022).
  
|Feature|Enterprise|Standard|Web|Express with Advanced Services|Express with Tools|Express|Enterprise Developer|Standard Developer|  
|-|-|-|-|-|-|-|-|-|  
|Standard algorithms|Yes|Yes|||||Yes|Yes|
|Data mining tools (Wizards, Editors,  Query Builders)|Yes|Yes|||||Yes|Yes|
|Cross validation|Yes||||||Yes||
|Models on filtered subsets of mining structure data|Yes||||||Yes||
|Time series: Custom blending between ARTXP and ARIMA methods|Yes||||||Yes||
|Time series: Prediction with new data|Yes||||||Yes||
|Unlimited concurrent DM queries|Yes||||||Yes||
|Advanced configuration & tuning options for data mining algorithms|Yes||||||Yes||
|Support for plug-in algorithms|Yes||||||Yes||
|Parallel model processing|Yes||||||Yes||
|Time series: cross-series prediction|Yes||||||Yes||
|Unlimited attributes for association rules|Yes||||||Yes||
|Sequence prediction|Yes||||||Yes||
|Multiple prediction targets for naïve Bayes, neural network and logistic regression|Yes||||||Yes||
  
::: moniker-end

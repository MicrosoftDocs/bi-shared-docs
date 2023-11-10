---
title: "Comparing Analysis Services tabular and multidimensional models | Microsoft Docs"
description: Describes the differences between Analysis Services multidimensional and tabular model solutions.
ms.date: 01/19/2022
ms.service: analysis-services
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || >= sql-analysis-services-2016"
---
# Comparing tabular and multidimensional solutions

[!INCLUDE[appliesto-sqlas](includes/appliesto-sqlas.md)]

SQL Server Analysis Services (SSAS) provides several approaches, or modes, for creating business intelligence semantic models: Tabular and Multidimensional.

Multidimensional mode is *only* available with SQL Server Analysis Services. If you want your models deployed to Azure Analysis Services or Power BI, you can stop reading now. **Multidimensional models will not be supported in Azure Analysis Services or Power BI Premium semantic models**. If you want multidimensional models in the cloud, the only way is to deploy SQL Server Analysis Services in Multidimensional mode to an Azure VM.

Because multidimensional models are only supported in SQL Server Analysis Services, this article is not meant to be a comparison of Analysis Services platforms (SQL Server, Azure, Power BI). It is meant to provide a high-level comparison of multidimensional and tabular model constructs entirely in context of SQL Server Analysis Services.

SQL Server Analysis Services also includes Power Pivot for SharePoint mode, which remains supported for SharePoint 2016 and SharePoint 2013, however, Microsoft's BI strategy has shifted away from Power Pivot in Excel integration with SharePoint. Power BI and Power BI Report Server are now the recommended platforms to host Excel workbooks with Power Pivot models. As such, this article now excludes a Power Pivot for SharePoint comparison.
  
In SQL Server Analysis Services, having more than one approach enables a modeling experience tailored to different business and user requirements. Multidimensional is a mature technology built on open standards, embraced by numerous vendors of BI software, but can be challenging to implement. Tabular offers a relational modeling approach that many developers find more intuitive. In the long run, tabular models are easier to develop and easier to manage. While multidimensional models are still prevalent in many BI solutions, tabular models are now more widely accepted as the standard enterprise-grade BI semantic modeling solution on Microsoft platforms.
  
All models are deployed as databases that run on an Analysis Services instance, or with tabular models, deployed as a *semantic model* to a Power BI Premium capacity. Models are accessed by client applications or services like Power BI. Model data is visualized in interactive and static reports via Excel, Reporting Services, Power BI, and BI tools from other vendors.  
  
Tabular and multidimensional solutions created by using Visual Studio and are intended for corporate BI solutions that run on an SQL Server Analysis Services instance on-premises, and for tabular models, an Azure Analysis Services server resource or as a semantic model in a [Power BI Premium](/power-bi/admin/service-premium-what-is) capacity. Each solution yields high performance analytical databases that integrate easily with clients applications and data visualizations services. Yet each solution differs in how they are created, used, and deployed. The bulk of this article compares these two types so that you can identify the right approach for you.  
  
## Overview of modeling types

 The following table enumerates the different models, summarizes the approach, initial release, and supported compatibility level.  
  
|Type|Modeling description|Initially released| Compatibility level|
|-|-|-|-|
|Multidimensional|OLAP modeling constructs (cubes, dimensions, measures).|SQL Server 2000  </br> SQL Server 2012 and later|  1050 </br> 1100 |
|Power Pivot|Originally an add-in, but now fully integrated into Excel. Tabular model infrastructure. APIs and scripting not supported.|  SQL Server 2008 R2| N\A |
|Tabular|Relational modeling constructs (model, tables, columns). Internally, metadata is inherited from OLAP modeling constructs (cubes, dimensions, measures). Code and script use OLAP metadata.|SQL Server 2012 </br> SQL Server 2014 |  1050  </br>  1103  |
|Tabular in SQL Server 2016 and later|Relational modeling constructs (model, tables, columns), articulated in tabular metadata object definitions in [Tabular Model Scripting Language (TMSL)](/analysis-services/tmsl/tabular-model-scripting-language-tmsl-reference) and [Tabular Object Model (TOM)](tom/introduction-to-the-tabular-object-model-tom-in-analysis-services-amo.md) code.|SQL Server 2016</br> SQL Server 2014</br> SQL Server 2019</br> SQL Server 2022| 1200 </br> 1400 </br> 1500</br> 1600|
|Tabular in Azure Analysis Services <sup>[1](#aas)</sup>|Relational modeling constructs (model, tables, columns), articulated in tabular metadata object definitions in [Tabular Model Scripting Language (TMSL)](/analysis-services/tmsl/tabular-model-scripting-language-tmsl-reference) and [Tabular Object Model (TOM)](tom/introduction-to-the-tabular-object-model-tom-in-analysis-services-amo.md) code.|2016| 1200 and higher |
|Tabular in Power BI Premium <sup>[2](#pbip)</sup> |Relational modeling constructs (model, tables, columns), articulated in tabular metadata object definitions in [Tabular Model Scripting Language (TMSL)](/analysis-services/tmsl/tabular-model-scripting-language-tmsl-reference) and [Tabular Object Model (TOM)](tom/introduction-to-the-tabular-object-model-tom-in-analysis-services-amo.md) code.|2020 | 1500 and higher |

<a name="aas">[1]</a> Azure Analysis Services supports tabular models at the 1200 and higher compatibility levels. However, not all tabular modeling functionality described in this article is supported. While creating and deploying tabular models to Azure Analysis Services is much the same as it is for on-premises, it's important to understand the differences. To learn more, see [What is Azure Analysis Services?](/azure/analysis-services/analysis-services-overview)

<a name="pbip">[2]</a> Power BI Premium capacities support tabular models at the 1500 and higher compatibility levels. However, not all tabular modeling functionality described in this article is supported. While creating and deploying tabular models to Power BI Premium is much the same as it is for on-premises or Azure, it's important to understand the differences. To learn more, see [Analysis Services in Power BI Premium](/power-bi/admin/service-premium-what-is#analysis-services-in-power-bi-premium-preview)

Compatibility level is important. It refers to release-specific behaviors in the Analysis Services engine. To learn more, see [Tabular model compatibility level](tabular-models/compatibility-level-for-tabular-models-in-analysis-services.md) and [Multidimensional model compatibility level](multidimensional-models/compatibility-level-of-a-multidimensional-database-analysis-services.md)
  
## Model features

The following table summarizes feature availability at the model level. Review this list to ensure that the feature you want to use is available in the type of model you plan to build.  

| Feature | Multidimensional | Tabular |
|-------- | ---------------- | ------- |
|Actions|Yes|No|
|Aggregations|Yes|No|
|Calculated Column|No|Yes|  
|Calculated Measures|Yes|Yes|
|Calculated Tables|No|Yes<sup>[3](#cl)</sup>|  
|Custom Assemblies|Yes|No|
|Custom Rollups|Yes|No| 
|Default Member|Yes|No|  
|Display folders|Yes|Yes<sup>[3](#cl)</sup>|  
|Distinct Count|Yes|Yes (via DAX)|
|Drillthrough|Yes|Yes (depends on client application)|
|Hierarchies|Yes|Yes|
|KPIs|Yes|Yes| 
|Linked objects|Yes|Yes (linked tables)|
|M expressions|No|Yes<sup>[3](#cl)</sup>|
|Many-to-many relationships|Yes|No (but there is [bi-directional cross filters](../analysis-services/tabular-models/bi-directional-cross-filters-tabular-models-analysis-services.md) at 1200 and higher compatibility levels)| 
|Named sets|Yes|No| 
|Ragged Hierarchies|Yes|Yes<sup>[3](#cl)</sup>|  
|Parent-child Hierarchies|Yes|Yes (via DAX)|
|Partitions|Yes|Yes| 
|Perspectives|Yes|Yes|
|Query interleaving|No|Yes<sup>[4](#platform)</sup>|
|Row-level Security|Yes|Yes| 
|Object-level Security|Yes|Yes<sup>[3](#cl)</sup>|
|Semi-additive Measures|Yes|Yes|
|Translations|[Yes](../analysis-services/multidimensional-models/translations-in-multidimensional-models-analysis-services.md)|Yes| 
|User-defined Hierarchies|Yes|Yes|
|Writeback|Yes|No|
  
 <a name="cl">[3]</a> For information about functional differences between compatibility levels, see [Compatibility Level for tabular models in Analysis Services](../analysis-services/tabular-models/compatibility-level-for-tabular-models-in-analysis-services.md).  

<a name="platform">[4]</a>  - SQL Server 2019 and later Analysis Services, Azure Analysis Services.
  
## Data Considerations

 Tabular and multidimensional models use imported data from external sources. The amount and type of data you need to import can be a primary consideration when deciding which model type best fits your data.  
  
### Compression
  
 Both tabular and multidimensional solutions use data compression that reduces the size of the Analysis Services database relative to the data warehouse from which you are importing data. Because actual compression will vary based on the characteristics of the underlying data, there is no way to know precisely how much disk and memory will be required by a solution after data is processed and used in queries.  
  
 An estimate used by many Analysis Services developers is that primary storage of a multidimensional database will be about one third size of the original data. Tabular databases can sometimes get greater amounts of compression, about one tenth the size, especially if most of the data is imported from fact tables.  
  
### Size of the model and resource bias (in-memory or disk)  
  
 The size of an Analysis Services database is constrained only by the resources available to run it. The model type and storage mode will also play a role in how large the database can grow.  
  
 Tabular databases run either in-memory or in DirectQuery mode that offloads query execution to an external database. For tabular in-memory analytics, the database is stored entirely in memory, which means you must have sufficient memory to not only load all the data, but also  additional data structures created to support queries.  
  
 DirectQuery, revamped in SQL Server 2016, has fewer restrictions than before, and better performance. Leveraging the backend relational database for storage and query execution makes building a large scale Tabular model more feasible than was previously possible.  
  
 Historically, the largest databases in production are multidimensional, with processing and query workloads running independently on dedicated hardware, each one optimized for its respective use.  Tabular databases are catching up quickly, and new advancements in DirectQuery will help close the gap even further.  
  
 For multidimensional offloading data storage and query execution is available via ROLAP.   On a query server, rowsets can be cached, and stale ones  paged out. Efficient and balanced use of memory and disk resources often guide customers to multidimensional solutions.  
  
 Under load, both disk and memory requirements for either solution type can be expected to increase as Analysis Services caches, stores, scans, and queries data. For more information about memory paging options, see [Memory Properties](../analysis-services/server-properties/memory-properties.md). To learn more about scale, see [High availability and Scalability in Analysis Services](../analysis-services/instances/high-availability-and-scalability-in-analysis-services.md).  
  
### Supported data sources  
  
 Tabular models can import data from relational data sources, data feeds, and some document formats. You can also use OLE DB for ODBC providers with tabular models. Tabular models at the 1400 and higher compatibility levels offer a significant increase in the variety of data sources from which you can import from. This is due to the introduction of the modern Get Data data query and import features in Visual Studio utilizing the M formula query language.

Multidimensional solutions can import data from relational data sources using OLE DB native and managed providers.  
  
 To view the list of external data sources that you can import to each model, see the following topics:  
  
- [Data sources supported (Tabular)](../analysis-services/tabular-models/data-sources-supported-ssas-tabular.md)  

- [Supported data sources (Multidimensional)](../analysis-services/multidimensional-models/supported-data-sources-ssas-multidimensional.md)  
  
## Query and scripting language support

Analysis Services includes MDX, DMX, DAX, XML/A, ASSL, and TMSL. Support for these languages can vary by model type. If query and scripting language requirements are a consideration, review the following list.  

- Tabular model databases support DAX calculations, DAX queries, and MDX queries. This is true at all compatibilities levels. Scripting languages are ASSL (over XMLA) for compatibility levels 1050-1103, and TMSL (over XMLA) for compatibility level 1200 and higher.
  
- Multidimensional model databases support MDX calculations, MDX queries, DAX queries, and ASSL.
  
- Analysis Services PowerShell is supported for tabular and multidimensional models and databases.  
  
All databases support XMLA.  
  
## Security features

All Analysis Services solutions can be secured at the database level. More granular security options vary by mode. If granular security settings are requirement for your solution, review the following list to ensure the level of security you want is supported in the type of solution you want to build:  

- Tabular model databases can use row-level and object-level security, using [role-based permissions](tabular-models/roles-ssas-tabular.md).  
  
- Multidimensional model databases can use dimension and cell-level security, using [role-based permissions](multidimensional-models/roles-and-permissions-analysis-services.md).  
  
## Design tools

Visual Studio with Analysis Services projects extension, also known as SQL Server Data Tools (SSDT), is the primary tool used to create both multidimensional and tabular solutions. This authoring environment uses the Visual Studio shell to provide designer workspaces, property panes, and object navigation. Tabular models also support model authoring by open-source and third-party tools. To learn more, see [Analysis Services tools](tools-and-applications-used-in-analysis-services.md).

## Client application support

In-general, tabular and multidimensional solutions support client applications using one or more of the Analysis Services client libraries (MSOLAP, AMOMD, ADOMD). For example, Excel, Power BI Desktop, and custom applications. Data visualization and analytics services like Power BI fully support tabular and multidimensional solutions.

If you are using Reporting Services, report feature availability varies across editions and server modes. For this reason, the type of report that you want to build might influence which server mode you choose to install.  
  
[!INCLUDE[ssCrescent](includes/sscrescent-md.md)], a Reporting Services authoring tool that runs in SharePoint, is available on a report server that is deployed in a SharePoint 2010 farm. The only type of data source that can be used with this report is an Analysis Services tabular model database or a [!INCLUDE[ssGemini](includes/ssgemini-md.md)] workbook. This means that you must have a tabular mode server or a [!INCLUDE[ssGemini](includes/ssgemini-md.md)] for SharePoint server to host the data source used by this type of report. You cannot use a multidimensional model as a data source for a [!INCLUDE[ssCrescent](includes/sscrescent-md.md)] report. You must create a [!INCLUDE[ssGemini](includes/ssgemini-md.md)] BI Semantic Model connection or a Reporting Services shared data source to use as the data source for a [!INCLUDE[ssCrescent](includes/sscrescent-md.md)] report.  
  
Report Builder and Report Designer can use any Analysis Services database, including [!INCLUDE[ssGemini](includes/ssgemini-md.md)] workbooks that are hosted on [!INCLUDE[ssGemini](includes/ssgemini-md.md)] for SharePoint.  
  
Excel PivotTable reports are supported by all Analysis Services databases. Excel functionality is the same whether you use a tabular .database, multidimensional database, or [!INCLUDE[ssGemini](includes/ssgemini-md.md)] workbook, although Writeback is only supported for multidimensional databases.  

## See also

[Tabular model overview](tabular-models/tabular-models-ssas.md)  
[Multidimensional models](multidimensional-models/multidimensional-models-ssas.md)

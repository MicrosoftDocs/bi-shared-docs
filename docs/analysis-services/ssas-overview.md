---
title: SQL Server Analysis Services overview
description: Describes SQL Server Analysis Services.
ms.date: 03/21/2023
ms.service: analysis-services
ms.topic: overview
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || >= sql-analysis-services-2016"
---
# SQL Server Analysis Services overview

[!INCLUDE[appliesto-sqlas-all](includes/appliesto-sqlas-all.md)]

Analysis Services is an analytical data engine (VertiPaq) used in decision support and business analytics. It provides enterprise-grade semantic data models for business reports and client applications such as Power BI, Excel, Reporting Services reports, and other data visualization tools.

Installed as an on-premises or virtual machine server instance, SQL Server Analysis Services supports tabular models at all compatibility levels (depending on version), multidimensional models, data mining, and Power Pivot for SharePoint.

## SQL Server Analysis Services workflow

A typical implementation workflow includes installing a SQL Server Analysis Services instance, creating a tabular or multidimensional data model, deploying the model as a database to a server instance, processing the database to load it with data, and then assigning permissions to allow data access. When ready to go, the data model can be accessed by any client application supporting Analysis Services as a data source.

To create a model, use Visual Studio with Analysis Services projects extension, also known as SQL Server Data Tools or simply SSDT, choosing either a Tabular or Multidimensional project template. The project template contains folders for all of the objects needed in a model. You can use wizards to create all of the basic elements, such as data sources, data source views, dimensions, cubes, and roles. Visual Studio and DevOps supports efficient CI/CD pipelines.

Models are populated with data from external data systems, usually data warehouses hosted on a SQL Server or Oracle relational database engine (Tabular models support additional data source types). Models specify query objects, such as cubes, but also specify dimensions that can be used in multiple cubes, calculations and KPIs that encapsulate business logic, and interactions such as navigation and drill-through behaviors.

To use a model, it's deployed to a server instance that runs databases in a particular server mode, making the data available to authorized users who connect through Excel or other applications.

## Documentation

Analysis Services documentation is located in different areas in Microsoft Learn, depending on the platform or version you are using. All SQL Server Analysis Services documentation is accessible by using the Table of Contents to the left. To see only those articles relevant to a particular version, use the **Version** selector above the ToC.

![version selector](media/ssas-overview/version-selector-ssas.png)

Documentation you see in the ToC to the left is known as the core Analysis Services documentation. Core documentation can apply to just one platform, like SQL Server Analysis Services, or to all Analysis Services platforms including Azure Analysis Services and Analysis Services in Power BI. This is because how you create and deploy a tabular model, or manage certain server properties or databases is much the same, regardless of platform.

In the core documentation, at the top of each article an **APPLIES TO** banner indicates the platforms and versions the article applies to. Keep in mind, feature and functionality changes are happening to each platform all the time. When they do, we make every effort to update the documentation.

Looking for **SQL Server 2014 Analysis Services** documentation? - SQL Server 2014 Analysis Services documentation is kept separate from later version documentation. This is due to changing documentation models used on Microsoft technical documentation compared to MSDN, where SQL Server 2014 and earlier Books Online documentation was originally published. Go to [SQL Server 2014 Analysis Services documentation](/sql/analysis-services/analysis-services?preserve-view=true&view=sql-server-2014). Keep in mind, SQL Server 2014 is no longer in mainstream support. Need to go back even further? See [SQL Server previous versions documentation](/previous-versions/sql/).

## See also

[What's new in SQL Server Analysis Services](what-s-new-in-sql-server-analysis-services.md)

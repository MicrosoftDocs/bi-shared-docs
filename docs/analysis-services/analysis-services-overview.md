---
title: "What is Analysis Services?"
description: Describes the three platforms for Analysis Services.
ms.date: 12/19/2023
ms.service: analysis-services
ms.topic: overview
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# What is Analysis Services?

[!INCLUDE[appliesto-sqlas-all-aas-pbip](includes/appliesto-sqlas-all-aas-pbip.md)]

Analysis Services is an analytical data engine (VertiPaq) used in decision support and business analytics. It provides enterprise-grade semantic data model capabilities for business intelligence (BI), data analysis, and reporting applications such as Fabric/Power BI, Excel, Reporting Services, and other data visualization tools. Analysis Services is available in different platforms:

**Power BI** - The Analysis Services engine supports the semantic model (previously known as dataset) artifact in [Power BI](/power-bi/fundamentals/power-bi-overview). Semantic models are created in Power BI Desktop and then published to the Power BI service. Any number of reports can then be created using the model and those reports can be shared across the organization in the Power BI service.

The Analysis Service engine also provides programmability, client application, and tool support for **Power BI Premium** and **Premium Per User** semantic models through client libraries and APIs that support the open-standard XMLA protocol. Premium models support connections through XMLA endpoints for *read-only* and *read-write* operations from Microsoft and third-party client applications and tools. To learn more, see [What is Power BI Premium](/power-bi/service-premium-what-is#analysis-services-in-power-bi-premium) and [Semantic model connectivity with the XMLA Endpoint](/power-bi/service-premium-connect-tools).

**Microsoft Fabric** - Microsoft Fabric includes Power BI. And much like Power BI, the Analysis Services engine supports Microsoft Fabric semantic models. The [Lakehouse](/fabric/data-engineering/lakehouse-overview) architecture in Microsoft Fabric includes the concept of a *default semantic model* in the SQL endpoint, also supported by Analysis Services. Unique in Microsoft Fabric, with Lakehouse delta tables you have the option to use *Direct Lake storage mode*. Direct Lake mode is a groundbreaking data access technology for semantic models based on loading Delta-Parquet files directly from OneLake without having to import or duplicate the data. Direct Lake combines the advantages of DirectQuery and Import modes to deliver fast query performance without any data movement. To learn more, see [What is Microsoft Fabric](/fabric/get-started/microsoft-fabric-overview) and [Learn about Direct Lake in Power BI and Microsoft Fabric](/power-bi/enterprise/directlake-overview).

**Azure Analysis Services** - Created as an Azure resource, Azure Analysis Services server resources support tabular models at the 1200 and higher compatibility levels. DirectQuery, partitions, row-level security, bi-directional relationships, and translations are all supported. To learn more, see [What is Azure Analysis Services](/azure/analysis-services/analysis-services-overview).

**SQL Server Analysis Services** - Installed as an on-premises or VM server instance, SQL Server Analysis Services supports tabular models at all compatibility levels (depending on version), multidimensional models, and Power Pivot for SharePoint. To learn more, see [SQL Server Analysis Services overview](ssas-overview.md).

## Documentation

Analysis Services documentation is located in different areas of Microsoft Learn, depending on the platform or version you're using. To learn more, see [Understanding Analysis Services documentation](analysis-services-docs.md).

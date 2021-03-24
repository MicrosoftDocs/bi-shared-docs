---
title: "What is Analysis Services? | Microsoft Docs"
description: Describes the three platforms for Analysis Services.
ms.date: 03/24/2021
ms.prod: sql
ms.technology: analysis-services
ms.topic: overview
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# What is Analysis Services?

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

Analysis Services is an analytical data engine (Vertipaq) used in decision support and business analytics. It provides enterprise-grade semantic data model capabilities for business intelligence (BI), data analysis, and reporting applications such as Power BI, Excel, Reporting Services, and other data visualization tools. Analysis Services is available in different platforms:

**Azure Analysis Services** - Created as an Azure resource, Azure Analysis Services server resources support tabular models at the 1200 and higher compatibility levels. DirectQuery, partitions, row-level security, bi-directional relationships, and translations are all supported. To learn more, see [What is Azure Analysis Services](/azure/analysis-services/analysis-services-overview).

**Power BI Premium** - The Analysis Services Vertipaq engine provides programmability, client application, and tool support for Power BI Premium and Premium Per User datasets at the 1500 and higher compatibility levels through client libraries and APIs that support the open-standard XMLA protocol. Power BI Premium datasets support connections through XMLA endpoints for *read-only* and *read-write* operations from Microsoft and third-party client applications and tools. To learn more, see [Analysis Services in Power BI Premium](/power-bi/service-premium-what-is#analysis-services-in-power-bi-premium-preview) and [Power BI Premium dataset connectivity with the XMLA Endpoint](/power-bi/service-premium-connect-tools).

**SQL Server Analysis Services** - Installed as an on-premises or VM server instance, SQL Server Analysis Services supports tabular models at all compatibility levels (depending on version), multidimensional models, data mining, and Power Pivot for SharePoint.

## Documentation

Analysis Services documentation is located at different places in docs.microsoft.com depending on the platform or version you're using. To learn more, see [Understanding Analysis Services documentation](analysis-services-docs.md).

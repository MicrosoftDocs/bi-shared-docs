---
title: "Data providers used for Analysis Services connections | Microsoft Docs"
ms.date: 04/21/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom:
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Client libraries (data providers) used for Analysis Services connections

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

Analysis Services provides three client libraries, also known as **data providers**, for server and data access from tools and client applications. Tools like SQL Server Management Studio (SSMS) and Visual Studio, and applications like Power BI Desktop and Excel connect to Analysis Services by using these libraries. Two of the client libraries, ADOMD.NET and Analysis Services Management Objects (AMO), are managed client libraries. The Analysis Services OLE DB provider (MSOLAP DLL) is a native client library. Client libraries are the same for both SQL Server Analysis Services and Azure Analysis Services.
  
## Where to get newer versions

The version installed on a client computer should match the major version of the server providing the data. If the server installation is newer than the data providers installed on the workstations in your network, you might need to install newer libraries.  

Client libraries included in earlier SQL Server Feature Packs correspond to that SQL version; however, they may not be the latest. Connecting to Azure Analysis Services may require later versions. All versions are backward compatible.

To get the latest,  see [Client libraries for connecting to Azure Analysis Services](https://docs.microsoft.com/azure/analysis-services/analysis-services-data-providers).

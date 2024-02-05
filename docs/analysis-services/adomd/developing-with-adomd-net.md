---
title: "Developing with ADOMD.NET | Microsoft Docs"
description: Learn how  ADOMD.NET is a Microsoft .NET Framework data provider designed to communicate with Microsoft SQL Server Analysis Services (SSAS).
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: adomd
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# ADOMD.NET

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

  ADOMD.NET is a Microsoft .NET Framework data provider designed to communicate with Analysis Services. ADOMD.NET uses the XML for Analysis protocol to communicate with analytical data sources by using either TCP/IP or HTTP connections to transmit and receive SOAP requests and responses that are compliant with the XML for Analysis specification. Commands can be sent in Multidimensional Expressions (MDX), Data Mining Extensions (DMX), Analysis Services Scripting Language (ASSL), or even a limited syntax of SQL, and may not return a result. Analytical data, key performance indicators (KPIs), and mining models can be queried and manipulated by using the ADOMD.NET object model. By using ADOMD.NET, you can also view and work with metadata either by retrieving OLE DB-compliant schema rowsets or by using the ADOMD.NET object model.  
  
 The ADOMD.NET data provider is represented by the **Microsoft.AnalysisServices.AdomdClient** namespace.  
  
## In This Section  
  
|Topic|Description|  
|-----------|-----------------|  
|[ADOMD.NET Client Programming](multidimensional-models-adomd-net-client/adomd-net-client-programming.md)|Describes how to use ADOMD.NET client objects to retrieve data and metadata from analytical data sources.|  
|[ADOMD.NET Server Programming](multidimensional-models-adomd-net-server/adomd-net-server-programming.md)|Describes how to use ADOMD.NET server objects to create stored procedures and user-defined functions.|  
|[Redistributing ADOMD.NET](redistributing-adomd-net.md)|Describes the process of redistributing ADOMD.NET.|  
|<xref:Microsoft.AnalysisServices.AdomdClient>|Details the objects that are contained in the **Microsoft.AnalysisServices.AdomdClient** namespace.|

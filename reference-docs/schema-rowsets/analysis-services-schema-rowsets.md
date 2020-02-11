---
title: "Analysis Services Schema Rowsets | Microsoft Docs"
ms.date: 02/11/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: schema-rowsets
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Analysis Services Schema Rowsets

[!INCLUDE[ssasyes-aasyes-pbiyes](../includes/ssasyes-aasyes-pbiyes.md)]

  Schema rowsets are predefined tables that contain information about Analysis Services objects and server state, including database schema, active sessions, connections, commands, and jobs that are executing on the server. You can query schema rowset tables in an XML/A script window in SQL Server Management Studio, run a DMV query against a schema rowset, or create a custom application that incorporates schema rowset information (for example, a reporting application that retrieves the list of available dimensions that can be used to create a report).  
  
> [!NOTE]  
>  If you are using schema rowsets in XML/A script, the information that is returned in the *Result* parameter of the [Discover](../xmla/xml-elements-methods-discover.md) method is structured according to the rowset column layouts described in this section. The  XML for Analysis (XMLA) provider supports rowsets required by the XML for Analysis Specification. The XMLA provider also supports some of the standard schema rowsets for OLE DB, OLE DB for OLAP, and OLE DB for Data Mining data source providers. The supported rowsets are described in the following topics.  
  
## Schema rowsets

Schema rowsets are described in two SQL Server Analysis Services protocols:   

[[MS-SSAS-T]: SQL Server Analysis Services Tabular Protocol](https://msdn.microsoft.com/library/mt719260) - Describes schema rowsets for tabular models at the 1200 and higher compatibility levels.

[[MS-SSAS]: SQL Server Analysis Services Protocol](https://msdn.microsoft.com/library/ee320606) - Describes schema rowsets for multidimensional models and tabular models.
  
  

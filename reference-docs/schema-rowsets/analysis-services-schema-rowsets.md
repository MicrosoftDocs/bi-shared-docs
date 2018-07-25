---
title: "Analysis Services Schema Rowsets | Microsoft Docs"
ms.date: 07/25/2018
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

  Schema rowsets are predefined tables that contain information about Analysis Services objects and server state, including database schema, active sessions, connections, commands, and jobs that are executing on the server. You can query schema rowset tables in an XML/A script window in SQL Server Management Studio, run a DMV query against a schema rowset, or create a custom application that incorporates schema rowset information (for example, a reporting application that retrieves the list of available dimensions that can be used to create a report).  
  
> [!NOTE]  
>  If you are using schema rowsets in XML/A script, the information that is returned in the *Result* parameter of the [Discover](../xmla/xml-elements-methods-discover.md) method is structured according to the rowset column layouts described in this section. The XML for Analysis (XMLA) provider supports rowsets required by the XML for Analysis Specification. The XMLA provider also supports some of the standard schema rowsets for OLE DB, OLE DB for OLAP, and OLE DB for Data Mining data source providers. The supported rowsets are described in the following topics.  
  
## In This Section  
  
|Topic|Description|  
|-----------|-----------------|  
|[XML for Analysis Schema Rowsets](xml/xml-for-analysis-schema-rowsets.md)|Describes the XMLA rowsets supported by the XMLA provider.|  
|[OLE DB Schema Rowsets](ole-db/ole-db-schema-rowsets.md)|Describes the OLE DB schema rowsets supported by the XMLA provider.|  
|[OLE DB for OLAP Schema Rowsets](ole-db-olap/ole-db-for-olap-schema-rowsets.md)|Describes the OLE DB for OLAP schema rowsets supported by the XMLA provider.|  
|[Data Mining Schema Rowsets](data-mining/data-mining-schema-rowsets.md)|Describes the data mining schema rowsets supported by the XMLA provider.| 
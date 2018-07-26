---
title: "DISCOVER_KEYWORDS Rowset (XMLA) | Microsoft Docs"
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
# DISCOVER_KEYWORDS Rowset (XMLA)

  Returns information about keywords reserved by the Microsoft XML for Analysis (XMLA) provider.  
  
 If you call the [Discover](../../xmla/xml-elements-methods-discover.md) method with the **DISCOVER_KEYWORDS** enumeration value in the [RequestType](../../xmla/xml-elements-properties/requesttype-element-xmla.md) element, the **Discover** method returns the **DISCOVER_KEYWORDS** rowset.  
  
## Rowset Columns  
 The **DISCOVER_KEYWORDS** rowset contains the following columns.  
  
|Column name|Type indicator|Length|Description|  
|-----------------|--------------------|------------|-----------------|  
|**Keyword**|**DBTYPE_WSTR**||A list of all the keywords reserved by a provider.<br /><br /> Example: **AND**|  
  
 This schema rowset is not sorted.  
  
## Restriction Columns  
 The **DISCOVER_KEYWORDS** rowset can be restricted on the columns listed in the following table.  
  
|Column name|Type indicator|Restriction State|  
|-----------------|--------------------|-----------------------|  
|**Keyword**|**DBTYPE_WSTR**|Optional.|  

---
title: "DISCOVER_KEYWORDS Rowset (OLE DB for OLAP) | Microsoft Docs"
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
# DISCOVER_KEYWORDS Rowset (OLE DB for OLAP)

  Enumerates a list of words reserved by the provider.  
  
## Rowset Columns  
 The DISCOVER_KEYWORDS rowset contains the following columns.  
  
|Column name|Type indicator|Length|Description|  
|-----------------|--------------------|------------|-----------------|  
|**Keyword**|**DBTYPE_WSTR**||A reserved keyword.|  
  
 This schema rowset is not sorted.  
  
## Restriction Columns  
 The DISCOVER_KEYWORDS rowset can be restricted on the columns listed in the following table.  
  
|Column name|Type indicator|Restriction State|  
|-----------------|--------------------|-----------------------|  
|**Keyword**|**DBTYPE_WSTR**|Optional.|  

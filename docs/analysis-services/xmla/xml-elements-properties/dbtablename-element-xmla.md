---
title: "DbTableName Element (XMLA) | Microsoft Docs"
description: Learn how the DbTableName element contains the name of the table used by the parent TableNotification element.
ms.date: 07/24/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# DbTableName Element (XMLA)

  Contains the name of the table used by the parent [TableNotification](../xml-elements-properties/tablenotification-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<TableNotification>  
   ...  
   <DbTableName>...</DbTableName>  
   ...  
</TableNotification>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[TableNotification](../xml-elements-properties/tablenotification-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  

---
title: "DbSchemaName Element (XMLA) | Microsoft Docs"
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
# DbSchemaName Element (XMLA)

  Contains the name of the schema used by the parent [TableNotification](../xml-elements-properties/tablenotification-element-xmla.md) element in the table identified by the [DbTableName](../xml-elements-properties/dbtablename-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<TableNotification>  
   ...  
   <DbSchemaName>...</DbSchemaName>  
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

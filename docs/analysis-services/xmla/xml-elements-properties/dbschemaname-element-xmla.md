---
title: "DbSchemaName Element (XMLA) | Microsoft Docs"
description: Learn how the DbSchemaName element contains the name of the schema used by the parent TableNotification element in the table identified by the DbTableName element.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference

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

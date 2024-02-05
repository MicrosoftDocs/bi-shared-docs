---
title: "TableNotification Element (XMLA) | Microsoft Docs"
description: Learn how the TableNotification element represents a table notification for a NotifyTableChange command.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# TableNotification Element (XMLA)

  Represents a table notification for a [NotifyTableChange](../xml-elements-commands/notifytablechange-element-xmla.md) command.  
  
## Syntax  
  
```xml  
  
<TableNotifications>  
   ...  
   <TableNotification>  
      <DbSchemaName>...</DbSchemaName>  
      <DbTableName>...</DbTableName>  
   </TableNotification>  
   ...  
</TableNotifications>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[TableNotifications](../xml-elements-properties/tablenotifications-element-xmla.md)|  
|Child elements|[DbSchemaName](../xml-elements-properties/dbschemaname-element-xmla.md), [DbTableName](../xml-elements-properties/dbtablename-element-xmla.md)|  
  
## Remarks  

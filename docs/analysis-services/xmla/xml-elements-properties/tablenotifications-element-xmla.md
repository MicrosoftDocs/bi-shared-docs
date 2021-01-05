---
title: "TableNotifications Element (XMLA) | Microsoft Docs"
description: Learn how the TableNotifications element contains a collection of TableNotification elements used by the NotifyTableChange command. 
ms.date: 01/05/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# TableNotifications Element (XMLA)

  Contains a collection of [TableNotification](../xml-elements-properties/tablenotification-element-xmla.md) elements used by the [NotifyTableChange](../xml-elements-commands/notifytablechange-element-xmla.md) command.  
  
## Syntax  
  
```xml  
  
<NotifyTableChange >  
   ...  
   <TableNotifications>  
      <TableNotification>...</TableNotification>  
   </TableNotifications>  
   ...  
</NotifyTableChange>  
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
|Parent elements|[NotifyTableChange](../xml-elements-commands/notifytablechange-element-xmla.md)|  
|Child elements|[TableNotification](../xml-elements-properties/tablenotification-element-xmla.md)|  
  
## Remarks  
  
---
title: "NotifyTableChange Element (XMLA) | Microsoft Docs"
description: Learn how the NotifyTableChange element notifies an instance of Analysis Services that a change has occurred to tables in a specified data source.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# NotifyTableChange Element (XMLA)

  Notifies an instance of Analysis Services that a change has occurred to tables in a specified data source.  
  
## Syntax  
  
```xml  
  
<Command>  
   <NotifyTableChange>  
      <Object>...</Object>  
      <TableNotifications>...</TableNotifications>  
   </NotifyTableChange>  
</Command>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Command](../xml-elements-properties/command-element-xmla.md)|  
|Child elements|[Object](../xml-elements-properties/object-element-xmla.md), [TableNotifications](../xml-elements-properties/tablenotifications-element-xmla.md)|  
  
## Remarks  
 The **NotifyTableChange** command allows a client application to explicitly notify an Analysis Services instance that one or more tables contained in a data source have been changed. For proactive caching, this notification indicates that relational OLAP (ROLAP) objects based on those tables should be reviewed and updated.  
  
 This method of notification is best used for ROLAP objects based on views or named queries defined in a data source view for which changes can be hard to detect and track.  
  
 The **Object** element must refer to a data source in the Analysis Services database. If the **Object** element refers to an object other than a data source, an error occurs.  

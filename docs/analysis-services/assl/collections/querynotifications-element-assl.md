---
title: "QueryNotifications Element (ASSL) | Microsoft Docs"
description: Learn about the QueryNotifications collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# QueryNotifications Element (ASSL)

  Contains the collection of [QueryNotification](../objects/querynotification-element-assl.md) elements that provide information to the [ProactiveCaching](../objects/proactivecaching-element-assl.md) element about queries to execute to determine whether a data source has been modified.  
  
## Syntax  
  
```xml  
  
<ProactiveCachingQueryBinding>  
   ...  
   <QueryNotifications>  
      <QueryNotification>...</QueryNotification>  
...</QueryNotifications>  
   ...  
</ProactiveCachingQueryBinding>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[ProactiveCachingQueryBinding](../data-type/proactivecachingquerybinding-data-type-assl.md)|  
|Child elements|[QueryNotification](../objects/querynotification-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.QueryNotificationCollection>.  


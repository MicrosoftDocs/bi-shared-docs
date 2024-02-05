---
title: "IncrementalProcessingNotifications Element (ASSL) | Microsoft Docs"
description: Learn about the IncrementalProcessingNotifications collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# IncrementalProcessingNotifications Element (ASSL)

  Contains the collection of [IncrementalProcessingNotification](../objects/incrementalprocessingnotification-element-assl.md) elements that provide information to the [ProactiveCaching](../objects/proactivecaching-element-assl.md) element about queries to execute to determine the progress of incremental processing.  
  
## Syntax  
  
```xml  
  
<ProactiveCachingIncrementalProcessingBinding>  
   <IncrementalProcessingNotifications>  
      <IncrementalProcessingNotification>...  
   ...</IncrementalProcessingNotification>  
   </IncrementalProcessingNotifications>  
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
|Parent elements|[ProactiveCachingIncrementalProcessingBinding](../data-type/proactivecachingincrementalprocessingbinding-data-type-assl.md)|  
|Child elements|[IncrementalProcessingNotification](../objects/incrementalprocessingnotification-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.IncrementalProcessingNotificationCollection>.  

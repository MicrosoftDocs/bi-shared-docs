---
title: "IncrementalProcessingNotification Element (ASSL) | Microsoft Docs"
description: Learn about the IncrementalProcessingNotification object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference

---
# IncrementalProcessingNotification Element (ASSL)

  Contains information for the [ProactiveCaching](../objects/proactivecaching-element-assl.md) element about a query to execute to determine the progress of incremental processing.  
  
## Syntax  
  
```xml  
  
<IncrementalProcessingNotifications>  
   <IncrementalProcessingNotification xsi:type="IncrementalProcessingNotification">...</IncrementalProcessingNotification>  
</IncrementalProcessingNotifications>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[IncrementalProcessingNotification](../data-type/incrementalprocessingnotification-data-type-assl.md)|  
|Default value|None|  
|Cardinality|1-n: Required element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[IncrementalProcessingNotifications](../collections/incrementalprocessingnotifications-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.IncrementalProcessingNotification>.  
  
## See Also  
 [ProactiveCachingQueryBinding Data Type &#40;ASSL&#41;](../data-type/proactivecachingquerybinding-data-type-assl.md)   
 [ProactiveCaching Element &#40;ASSL&#41;](../objects/proactivecaching-element-assl.md)   
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

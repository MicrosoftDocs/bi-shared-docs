---
title: "EventID Element (ASSL) | Microsoft Docs"
description: Learn about the EventID property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# EventID Element (ASSL)

  Uniquely identifies an [Event](../objects/event-element-assl.md) element that is to be captured as part of a [Trace](../objects/trace-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Event>  
  
      <EventID>...</EventID>  
  
</Event>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|1-1: Required element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Event](../objects/event-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element corresponding to the parent of **EventID** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.TraceEvent>.  
  
## See Also  
 [Events Element &#40;ASSL&#41;](../collections/events-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

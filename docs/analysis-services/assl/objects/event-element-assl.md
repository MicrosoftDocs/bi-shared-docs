---
title: "Event Element (ASSL) | Microsoft Docs"
description: Learn about the Event object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Event Element (ASSL)

  Defines an **Event** to be captured as part of a [Trace](../objects/trace-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Events>  
   <Event>  
      <EventID>...</EventID>  
      <Columns>...</Columns>  
   </Event>  
</Events>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|1-n: Required element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Events](../collections/events-element-assl.md)|  
|Child elements|[Columns](../collections/columns-element-assl.md), [EventID](../properties/eventid-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.TraceEvent>.  
  
## See Also  
 [Trace Element &#40;ASSL&#41;](../objects/trace-element-assl.md)   
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

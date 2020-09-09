---
title: "ColumnID Element (EventColumn) (ASSL) | Microsoft Docs"
description: Learn about the ColumnID property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# ColumnID Element (EventColumn) (ASSL)

  Contains the identifier (ID) of the column of information to be captured for an event as part of a [Trace](../objects/trace-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<EventColumn>  
   <ColumnID>...</ColumnID>  
</EventColumn>  
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
|Parent element|[EventColumn](../data-type/eventcolumn-data-type-assl.md)|  
|Child elements|None.|  
  
## Remarks  
 The element that corresponds to the parent of **ColumnID** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.TraceColumn>.  
  
## See Also  
 [Columns Element &#40;ASSL&#41;](../collections/columns-element-assl.md)   
 [Event Element &#40;ASSL&#41;](../objects/event-element-assl.md)   
 [Events Element &#40;ASSL&#41;](../collections/events-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

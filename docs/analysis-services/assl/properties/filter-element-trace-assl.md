---
title: "Filter Element (Trace) (ASSL) | Microsoft Docs"
description: Learn about the Filter trace property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# Filter Element (Trace) (ASSL)

  Contains an XML document fragment that describes the [Trace](../objects/trace-element-assl.md) filter.  
  
## Syntax  
  
```xml  
  
<Trace>  
   ...  
   <Filter>...</Filter>  
   ...  
</Trace>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[Trace](../objects/trace-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **Filter** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Trace>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)   
 [Traces Element &#40;ASSL&#41;](../collections/traces-element-assl.md)  
  
  

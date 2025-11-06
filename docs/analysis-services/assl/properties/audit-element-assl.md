---
title: "Audit Element (ASSL) | Microsoft Docs"
description: Learn about the Audit property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference

---
# Audit Element (ASSL)

  Specifies that a [Trace](../objects/trace-element-assl.md) element cannot drop any events, even if this results in degraded performance on the server.  
  
## Syntax  
  
```xml  
  
<Trace>  
   ...  
   <Audit>...</Audit>  
   ...  
</Trace>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Boolean|  
|Default value|**False**|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[Trace](../objects/trace-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **Audit** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Trace>.  
  
## See Also  
 [Traces Element &#40;ASSL&#41;](../collections/traces-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

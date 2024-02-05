---
title: "Enabled Element (ASSL) | Microsoft Docs"
description: Learn about the Enabled property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# Enabled Element (ASSL)

  Indicates whether the parent element is enabled.  
  
## Syntax  
  
```xml  
  
<CubeHierarchy> <!-- or ProactiveCaching -->  
   ...  
   <Enabled>...</Enabled>  
   ...  
</CubeHierarchy>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Boolean|  
|Default value|True|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[CubeHierarchy](../data-type/cubehierarchy-data-type-assl.md), [ProactiveCaching](../objects/proactivecaching-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The elements that correspond to the parents of **Enabled** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.CubeHierarchy> and <xref:Microsoft.AnalysisServices.ProactiveCaching>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

---
title: "ForceRebuildInterval Element (ASSL) | Microsoft Docs"
description: Learn about the ForceRebuildInterval property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# ForceRebuildInterval Element (ASSL)

  Determines the amount of time, starting when a fresh multidimensional OLAP (MOLAP) image becomes available, after which MOLAP imaging unconditionally starts.  
  
## Syntax  
  
```xml  
  
<ProactiveCaching>  
   ...  
   <ForceRebuildInterval>...</ForceRebuildInterval>  
   ...  
</ProactiveCaching>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|XML duration|  
|Default value|Infinite|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[ProactiveCaching](../objects/proactivecaching-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **ForceRebuildInterval** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ProactiveCaching>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

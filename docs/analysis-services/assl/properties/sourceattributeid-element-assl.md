---
title: "SourceAttributeID Element (ASSL) | Microsoft Docs"
description: Learn about the SourceAttributeID property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: eur

ms.topic: reference
author: eric-urban
ms.author: eur

---
# SourceAttributeID Element (ASSL)

  Contains the identifier (ID) of the source attribute on which the [Level](../objects/level-element-assl.md) element is based.  
  
## Syntax  
  
```xml  
  
<Level>  
   ...  
   <SourceAttributeID>...</SourceAttributeID>  
   ...  
</Level>  
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
|Parent element|[Level](../objects/level-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element corresponding to the parent of **SourceAttributeID** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Level>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

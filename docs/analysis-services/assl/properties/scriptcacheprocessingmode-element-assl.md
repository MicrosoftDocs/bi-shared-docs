---
title: "ScriptCacheProcessingMode Element (ASSL) | Microsoft Docs"
description: Learn about the ScriptCacheProcessingMode property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# ScriptCacheProcessingMode Element (ASSL)

  Indicates whether the server should build the script cache during processing or after processing.  
  
## Syntax  
  
```xml  
  
<Cube>  
   ...  
      <ScriptCacheProcessingMode>...</ScriptCacheProcessingMode>  
   ...  
</Cube>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Regular*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[Cube](../objects/cube-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Regular*|The server builds the script cache during processing.|  
|*Lazy*|The server builds the script cache after processing.|  
  
 The enumeration that corresponds to the allowed values for **ScriptCacheProcessingMode** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ScriptCacheProcessingMode>.  
  
 The element that corresponds to the parent of **ScriptCacheProcessingMode** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Cube>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

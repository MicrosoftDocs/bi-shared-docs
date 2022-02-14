---
title: "CacheMode Element (ASSL) | Microsoft Docs"
description: Learn about the CacheMode property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 09/14/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# CacheMode Element (ASSL)

  Determines the caching mechanism used for training data retrieved while processing a mining structure.  
  
## Syntax  
  
```xml  
  
<MiningStructure>  
   ...  
   <CacheMode>...</CacheMode>  
   ...  
</MiningStructure>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*KeepTrainingCases*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[MiningStructure](../objects/miningstructure-element-assl.md)|  
|Child elements|None|  
  
## Remarks

 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*KeepTrainingCases*|Training cases are cached during and after processing.|  
|*ClearAfterProcessing*|Training cases are cached during processing, but deleted after processing.|  
  
 The element that corresponds to the parent of **CacheMode** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MiningStructure>.  
  
## See Also

 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

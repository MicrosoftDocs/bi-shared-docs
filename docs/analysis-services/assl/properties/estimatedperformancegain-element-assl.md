---
title: "EstimatedPerformanceGain Element (ASSL) | Microsoft Docs"
description: Learn about the EstimatedPerformanceGain property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
---
# EstimatedPerformanceGain Element (ASSL)

  Contains the read-only percentage of estimated performance gain for the partition.  
  
## Syntax  
  
```xml  
  
<AggregationDesign>  
      ...  
   <EstimatedPerformanceGain>...</EstimatedPerformanceGain>  
   ...  
</AggregationDesign>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Integer|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[AggregationDesign](../objects/aggregationdesign-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element corresponding to the parent of **EstimatedPerformanceGain** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.AggregationDesign>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

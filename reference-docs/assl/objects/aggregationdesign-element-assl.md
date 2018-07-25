---
title: "AggregationDesign Element (ASSL) | Microsoft Docs"
ms.date: 07/25/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# AggregationDesign Element (ASSL)

  Defines a set of aggregation definitions that can be shared across multiple partitions in a database.  
  
## Syntax  
  
```xml  
  
<AggregationDesigns>  
   <AggregationDesign>  
      <ID>...</ID>  
      <Name>...</Name>  
            <Description>...</Description>  
      <EstimatedRows>...</EstimatedRows>  
      <Dimensions>...</Dimensions>  
            <Aggregations>...</Aggregation>  
      <EstimatedPerformanceGain>...</EstimatedPerformanceGain>  
      <Annotations>...</Annotations>  
   </AggregationDesign>  
</AggregationDesigns>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[AggregationDesigns](../collections/aggregationdesigns-element-assl.md)|  
|Child elements|[Aggregations](../collections/aggregations-element-assl.md), [Annotations](../collections/annotations-element-assl.md), [Description](../properties/description-element-assl.md), [Dimensions](../collections/dimensions-element-assl.md), [EstimatedPerformanceGain](../properties/estimatedperformancegain-element-assl.md), [EstimatedRows](../properties/estimatedrows-element-assl.md), [ID](../properties/id-element-assl.md), [Name](../properties/name-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.AggregationDesign>.  
  
## See Also  
 [Partition Element &#40;ASSL&#41;](../objects/partition-element-assl.md)   
 [Aggregation Element &#40;ASSL&#41;](../objects/aggregation-element-assl.md)   
 [Aggregations Element &#40;ASSL&#41;](../collections/aggregations-element-assl.md)   
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

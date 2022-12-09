---
title: "Aggregation Element (ASSL) | Microsoft Docs"
description: Learn about the Aggregation object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Aggregation Element (ASSL)

  Defines a single aggregation for a [Partition](../objects/partition-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Aggregations>  
      <Aggregation>  
      <ID>...</ID>  
      <Name>...</Name>  
      <Dimensions>...</Dimensions>  
            <Annotations>...</Annotations>  
      <Description>...</Description>  
   </Aggregation>  
</Aggregations>  
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
|Parent element|[Aggregations](../collections/aggregations-element-assl.md)|  
|Child elements|[Annotations](../collections/annotations-element-assl.md), [Description](../properties/description-element-assl.md), [Dimensions](../collections/dimensions-element-assl.md), [ID](../properties/id-element-assl.md), [Name](../properties/name-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Aggregation>.  
  
## See Also  
 [Partition Element &#40;ASSL&#41;](../objects/partition-element-assl.md)   
 [AggregationDesign Element &#40;ASSL&#41;](../objects/aggregationdesign-element-assl.md)   
 [MeasureGroup Element &#40;ASSL&#41;](../objects/measuregroup-element-assl.md)   
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

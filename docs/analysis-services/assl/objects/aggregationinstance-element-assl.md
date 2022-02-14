---
title: "AggregationInstance Element (ASSL) | Microsoft Docs"
description: Learn about the AggregationInstance object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# AggregationInstance Element (ASSL)

  Defines an aggregation instance for a partition.  
  
## Syntax  
  
```xml  
  
<AggregationInstances>  
   <AggregationInstance>  
      <AggregationType>...</AggregationType>  
      <AggregationID>...</AggregationID>  
      <Source>...</Source>  
      <Dimensions>...</Dimensions>  
      <Measures>...</Measures>  
      <Annotations>...</Annotations>  
   </AggregationInstance>  
</AggregationInstances>  
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
|Parent elements|[AggregationInstances](../collections/aggregationinstances-element-assl.md)|  
|Child elements|[AggregationID](../properties/aggregationid-element-assl.md), [AggregationType](../properties/aggregationtype-element-assl.md), [Annotations](../collections/annotations-element-assl.md), [Dimensions](../collections/dimensions-element-assl.md), [Measures](../collections/measures-element-assl.md), [Source](../properties/source-element-binding-assl.md)|  
  
## Remarks  
 When a [Partition](../objects/partition-element-assl.md) element uses an [AggregationDesign](../objects/aggregationdesign-element-assl.md) element to generate aggregations for that partition, each [Aggregation](../objects/aggregation-element-assl.md) in the **AggregationDesign** is instantiated for that partition. Multiple partitions can use the same aggregation design to generate multiple instances of a defined aggregation. The **AggregationInstance** element represents an instance of a defined aggregation.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.AggregationInstance>.  
  
## See Also  
 [Objects &#40;ASSL&#41;](objects-assl.md)  
  
  

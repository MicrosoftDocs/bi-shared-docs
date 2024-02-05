---
title: "Dimension Element (ASSL) | Microsoft Docs"
description: Learn about the Dimension object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Dimension Element (ASSL)

  Defines a dimension.  
  
## Syntax  
  
```xml  
  
<Dimensions>  
   <Dimension xsi:type="Dimension">...</Dimension> <!-- ancestor: Database -->  
   <!-- or -->  
   <Dimension xsi:type="AggregationDimension">...</Dimension> <!-- ancestor: Aggregation -->  
   <!-- or -->  
   <Dimension xsi:type="AggregationDesignDimension">...</Dimension> <!-- ancestor: AggregationDesign -->  
   <!-- or -->  
   <Dimension xsi:type="AggregationInstanceCubeDimension">...</Dimension> <!-- ancestor: AggregationInstance -->  
      <!-- or -->  
   <Dimension xsi:type="CubeDimension">...</Dimension> <!-- ancestor: Cube -->  
      <!-- or -->  
   <Dimension xsi:type="MeasureGroupDimension">...</Dimension> <!-- ancestor: MeasureGroup -->  
   <!-- or -->  
   <Dimension xsi:type="PerspectiveDimension">...</Dimension> <!-- ancestor: Perspective -->  
</Dimensions>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|See the table below.|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
|Ancestor or Parent|Data Type|  
|------------------------|---------------|  
|[Database](../objects/database-element-assl.md)|[Dimension](../data-type/dimension-data-type-assl.md)|  
|[Aggregation](../objects/aggregation-element-assl.md)|[AggregationDimension](../data-type/aggregationdimension-data-type-assl.md)|  
|[AggregationDesign](../objects/aggregationdesign-element-assl.md)|[AggregationDesignDimension](../data-type/aggregationdesigndimension-data-type-assl.md)|  
|[AggregationInstance](../objects/aggregationinstance-element-assl.md)|[AggregationInstanceCubeDimension](../data-type/aggregationinstancecubedimension-data-type-assl.md)|  
|[Cube](../objects/cube-element-assl.md)|[CubeDimension](../data-type/cubedimension-data-type-assl.md)|  
|[MeasureGroup](../objects/measuregroup-element-assl.md)|[MeasureGroupDimension](../data-type/measuregroupdimension-data-type-assl.md)|  
|[Perspective](../objects/perspective-element-assl.md)|[PerspectiveDimension](../data-type/perspectivedimension-data-type-assl.md)|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Dimensions](../collections/dimensions-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The corresponding elements in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.Dimension>, <xref:Microsoft.AnalysisServices.AggregationDimension>, <xref:Microsoft.AnalysisServices.AggregationDesignDimension>, <xref:Microsoft.AnalysisServices.CubeDimension>, <xref:Microsoft.AnalysisServices.MeasureGroupDimension>, and <xref:Microsoft.AnalysisServices.PerspectiveDimension>.  
  
## See Also  
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

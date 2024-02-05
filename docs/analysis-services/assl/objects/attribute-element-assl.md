---
title: "Attribute Element (ASSL) | Microsoft Docs"
description: Learn about the Attribute object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Attribute Element (ASSL)

  Contains the description of an attribute.  
  
## Syntax  
  
```xml  
  
<Attributes>  
   <Attribute xsi:type="AggregationAttribute">...</Attribute> <!-- ancestor: AggregationDimension -->  
   <!-- or -->  
   <Attribute xsi:type="AggregationDesignAttribute">...</Attribute> <!-- ancestor: AggregationDesignDimension -->  
   <!-- or -->  
   <Attribute xsi:type="AggregationInstanceAttribute">...</Attribute> <!-- ancestor: AggregationInstanceCubeDimension -->  
   <!-- or -->  
   <Attribute xsi:type="CubeAttribute">...</Attribute> <!--ancestor:  CubeDimension -->  
   <!-- or -->  
   <Attribute xsi:type="DimensionAttribute">...</Attribute> <!-- ancestor: Dimension -->  
   <!-- or -->  
   <Attribute xsi:type="MeasureGroupAttribute">...</Attribute> <!-- ancestor: RegularMeasureGroupDimension -->  
   <!-- or -->  
   <Attribute xsi:type="PerspectiveAttribute">...</Attribute> <!-- ancestor: PerspectiveDimension -->  
   <!-- or -->  
   <Attribute>  
      <AttributeID>...</AttributeID>  
   </Attribute> <!-- ancestor: RelationshipEnd -->  
</Attributes>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|See the table below.|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
|Ancestor or Parent|Data Type|  
|------------------------|---------------|  
|[AggregationDesignDimension](../data-type/aggregationdesigndimension-data-type-assl.md)|[AggregationDesignAttribute](../data-type/aggregationdesignattribute-data-type-assl.md)|  
|[AggregationDimension](../data-type/aggregationdimension-data-type-assl.md)|[AggregationAttribute](../data-type/aggregationattribute-data-type-assl.md)|  
|[AggregationInstanceCubeDimension](../data-type/aggregationinstancecubedimension-data-type-assl.md)|[AggregationInstanceAttribute](../data-type/aggregationinstanceattribute-data-type-assl.md)|  
|[CubeDimension](../data-type/cubedimension-data-type-assl.md)|[CubeAttribute](../data-type/cubeattribute-data-type-assl.md)|  
|[Dimension](../objects/dimension-element-assl.md)|[DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md)|  
|[RegularMeasureGroupDimension](../data-type/regularmeasuregroupdimension-data-type-assl.md)|[MeasureGroupAttribute](../data-type/measuregroupattribute-data-type-assl.md)|  
|[PerspectiveDimension](../data-type/perspectivedimension-data-type-assl.md)|[PerspectiveAttribute](../data-type/perspectiveattribute-data-type-assl.md)|  
|[RelationshipEnd](../data-type/relationshipend-data-type-assl.md)|\<Attribute><br />      \<[AttributeID](../properties/attributeid-element-assl.md)>...\</AttributeID>\</Attribute>|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Attributes](../collections/attributes-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The corresponding elements in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.AggregationDesignAttribute>, <xref:Microsoft.AnalysisServices.AggregationAttribute>, <xref:Microsoft.AnalysisServices.CubeAttribute>, <xref:Microsoft.AnalysisServices.DimensionAttribute>, <xref:Microsoft.AnalysisServices.MeasureGroupAttribute>, and <xref:Microsoft.AnalysisServices.PerspectiveAttribute>.  
  
## See Also  
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

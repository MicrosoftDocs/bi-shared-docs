---
title: "Attributes Element (ASSL) | Microsoft Docs"
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Attributes Element (ASSL)

  Contains the collection of attributes for the associated dimension.  
  
## Syntax  
  
```xml  
  
<AggregationDesignDimension> <!-- or one of the elements listed below in the Element Relationships table -->  
   ...  
   <Attributes>  
      <Attribute>...</Attribute>  
  </Attributes>  
   ...  
</AggregationDesignDimension>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[AggregationDesignDimension](data-type/aggregationdesigndimension-data-type-assl.md), [AggregationDimension](data-type/aggregationdimension-data-type-assl.md), [AggregationInstanceCubeDimension](data-type/aggregationinstancecubedimension-data-type-assl.md), [CubeDimension](data-type/cubedimension-data-type-assl.md), [Dimension](objects/dimension-element-assl.md), [PerspectiveDimension](data-type/perspectivedimension-data-type-assl.md), [RegularMeasureGroupDimension](data-type/regularmeasuregroupdimension-data-type-assl.md), [RelationshipEnd](data-type/relationshipend-data-type-assl.md)|  
|Child elements|[Attribute](objects/attribute-element-assl.md)|  
  
## Remarks  
 The corresponding elements in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.AggregationAttributeCollection>, <xref:Microsoft.AnalysisServices.AggregationDesignAttributeCollection>, <xref:Microsoft.AnalysisServices.AggregationInstanceAttributeCollection>, <xref:Microsoft.AnalysisServices.CubeAttributeCollection>, <xref:Microsoft.AnalysisServices.DimensionAttributeCollection>, <xref:Microsoft.AnalysisServices.MeasureGroupAttributeCollection>, and <xref:Microsoft.AnalysisServices.PerspectiveAttributeCollection>.  

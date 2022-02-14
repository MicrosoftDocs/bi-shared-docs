---
title: "CubeDimensionID Element (ASSL) | Microsoft Docs"
description: Learn about the CubeDimensionID property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# CubeDimensionID Element (ASSL)

  Identifies the [CubeDimension](../data-type/cubedimension-data-type-assl.md) element associated with the parent element.  
  
## Syntax  
  
```xml  
  
<AggregationDesignDimension> <!-- or one of the elements listed below in the Element Relationships table -->  
   ...  
   <CubeDimensionID>...</CubeDimensionID>  
   ...  
</AggregationDesignDimension>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|1-1: Required element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[AggregationDesignDimension](../data-type/aggregationdesigndimension-data-type-assl.md), [AggregationDimension](../data-type/aggregationdimension-data-type-assl.md), [AggregationInstanceCubeDimension](../data-type/aggregationinstancecubedimension-data-type-assl.md), [CubeAttributeBinding](../data-type/cubeattributebinding-data-type-assl.md), [CubeDimensionBinding](../data-type/cubedimensionbinding-data-type-assl.md), [CubeDimensionPermission](../data-type/cubedimensionpermission-data-type-assl.md), [MeasureGroupDimension](../data-type/measuregroupdimension-data-type-assl.md), [MeasureGroupDimensionBinding](../data-type/measuregroupdimensionbinding-data-type-assl.md), [PerspectiveDimension](../data-type/perspectivedimension-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The elements that correspond to the parents of **CubeDimensionID** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.AggregationDesignDimension>, <xref:Microsoft.AnalysisServices.AggregationDimension>, <xref:Microsoft.AnalysisServices.CubeAttributeBinding>, <xref:Microsoft.AnalysisServices.CubeDimensionBinding>, <xref:Microsoft.AnalysisServices.CubeDimensionPermission>, <xref:Microsoft.AnalysisServices.MeasureGroupDimension>, <xref:Microsoft.AnalysisServices.MeasureGroupDimensionBinding>, and <xref:Microsoft.AnalysisServices.PerspectiveDimension>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

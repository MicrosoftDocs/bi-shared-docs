---
title: "RegularMeasureGroupDimension Data Type (ASSL) | Microsoft Docs"
description: Learn about the RegularMeasureGroupDimension data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# RegularMeasureGroupDimension Data Type (ASSL)

  Defines a derived data type that represents a regular relationship between a dimension and a measure group.  
  
## Syntax  
  
```xml  
  
<RegularMeasureGroupDimension>  
   <!-- The following elements extend MeasureGroupDimension -->  
   <Cardinality>...</Cardinality>  
   <Attributes>...</Attributes>  
</RegularMeasureGroupDimension>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[MeasureGroupDimension](measuregroupdimension-data-type-assl.md)|  
|Derived data types|[ReferenceMeasureGroupDimension](referencemeasuregroupdimension-data-type-assl.md), [DegenerateMeasureGroupDimension](degeneratemeasuregroupdimension-data-type-assl.md)|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[Attributes](../collections/attributes-element-assl.md), [Cardinality](../properties/cardinality-element-assl.md)|  
|Derived elements|[Dimension](../objects/dimension-element-assl.md) ([Dimensions](../collections/dimensions-element-assl.md) collection)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.RegularMeasureGroupDimension>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  

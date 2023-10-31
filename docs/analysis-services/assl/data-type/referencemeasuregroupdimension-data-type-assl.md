---
title: "ReferenceMeasureGroupDimension Data Type (ASSL) | Microsoft Docs"
description: Learn about the ReferenceMeasureGroupDimension data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# ReferenceMeasureGroupDimension Data Type (ASSL)

  Defines a derived data type that represents a dimension that is indirectly related to the fact table through an intermediate dimension. (For example, a Sales measure group can reference a Geography dimension, which is related through the Customer dimension.)  
  
## Syntax  
  
```xml  
  
<ReferenceMeasureGroupDimension>  
   <!-- The following elements extend MeasureGroupDimension -->  
      <IntermediateCubeDimensionID>...</IntermediateCubeDimensionID>  
   <IntermediateGranularityAttributeID>...</IntermediateGranularityAttributeID>  
   <Materialization>...</Materialization>  
</ReferenceMeasureGroupDimension>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[MeasureGroupDimension](measuregroupdimension-data-type-assl.md)|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[IntermediateCubeDimensionID](../properties/intermediatecubedimensionid-element-assl.md), [IntermediateGranularityAttributeID](../properties/intermediategranularityattributeid-element-assl.md), [Materialization](../properties/materialization-element-assl.md)|  
|Derived elements|None|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ReferenceMeasureGroupDimension>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  

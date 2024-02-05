---
title: "MeasureGroupDimension Data Type (ASSL) | Microsoft Docs"
description: Learn about the MeasureGroupDimension data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# MeasureGroupDimension Data Type (ASSL)

  Defines an abstract primitive data type that represents the relationship between a dimension and a measure group.  
  
## Syntax  
  
```xml  
  
<MeasureGroupDimension>  
   <CubeDimensionID>...</CubeDimensionID>  
      <Annotations>...</Annotations>  
   <Source>...</Source>  
</MeasureGroupDimension>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|None|  
|Derived data types|[DataMiningMeasureGroupDimension](dataminingmeasuregroupdimension-data-type-assl.md), [DegenerateMeasureGroupDimension](degeneratemeasuregroupdimension-data-type-assl.md), [ManyToManyMeasureGroupDimension](manytomanymeasuregroupdimension-data-type-assl.md), [ReferenceMeasureGroupDimension](referencemeasuregroupdimension-data-type-assl.md), [RegularMeasureGroupDimension](regularmeasuregroupdimension-data-type-assl.md)|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[Annotations](../collections/annotations-element-assl.md), [CubeDimensionID](../properties/cubedimensionid-element-assl.md), [Source](../properties/source-element-binding-assl.md)|  
|Derived elements|[Dimension](../objects/dimension-element-assl.md) ([Dimensions](../collections/dimensions-element-assl.md) collection of [MeasureGroup](../objects/measuregroup-element-assl.md))|  
  
## Remarks  
 Each **MeasureGroupDimension** is a reference to one of the dimensions on the cube. These define which cube dimensions apply to the measure group.  
  
 The set of attributes that are provided determines the granularity (scope) at which the measures on the measure group are known. For example, measures that represent product sales are contained in the Sales measure group. Information for these measures is stored in the underlying data source on a monthly, rather than weekly or daily, granularity. In this case, only the Month attribute would be listed for the **MeasureGroupDimension** that describes the relationship between a time dimension and the Sales measure group. In rare cases, the granularity might be defined in terms of a set of attributes. For example, given the set of attributes {Day, Week, Month, Year}, where Day implies Week and Month, but Week does not imply Month, the measures contained in the Forecasts measure group might be known by Month and Week, but not by Day.  
  
 If no attribute is provided, it is as if only the key attribute for the dimension were listed (defining the lowest level of granularity). Each partition of a measure group must have the same granularity. The set of attributes listed should not be redundant with respect to the relationships between attributes. For example, if Month implies Year, the granularity is defined as Month, not Month and Year.  
  
 A **MeasureGroupDimension** needs to include a hierarchy only if it has something specific to indicate about it. (There is no way to select which hierarchies apply to a particular measure group). Similarly, it needs to include a [MeasureGroupAttribute](measuregroupattribute-data-type-assl.md) only if it has something specific to indicate about it.  
  
 Each hierarchy must be a subset of the hierarchies included on the [CubeDimension](cubedimension-data-type-assl.md). It is not possible to select the levels, though some levels might automatically be disabled depending upon the granularity of the measure group.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MeasureGroupDimension>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  

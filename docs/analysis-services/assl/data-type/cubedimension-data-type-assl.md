---
title: "CubeDimension Data Type (ASSL) | Microsoft Docs"
description: Learn about the CubeDimension data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# CubeDimension Data Type (ASSL)

  Defines a primitive data type that represents the relationship between a dimension and a cube.  
  
## Syntax  
  
```xml  
  
<CubeDimension>  
      <ID>...</ID>  
   <Name>...</Name>  
   <Translations>...</Translations>  
   <DimensionID>...</DimensionID>  
   <Visible>...</Visible>  
   <AllMemberAggregationUsage>...</AllMemberAggregationUsage>  
   <HierarchyUniqueNameStyle>...</HierarchyUniqueNameStyle>  
   <MemberUniqueNameStyle>...</MemberUniqueNameStyle>  
      <Attributes>...</Attributes>  
   <Hierarchies>...</Hierarchies>  
      <Annotations>...</Annotation>  
</CubeDimension>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|None|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[AllMemberAggregationUsage](../properties/allmemberaggregationusage-element-assl.md), [Annotations](../collections/annotations-element-assl.md), [Attributes](../collections/attributes-element-assl.md), [DimensionID](../properties/dimensionid-element-assl.md), [Hierarchies](../collections/hierarchies-element-assl.md), [HierarchyUniqueNameStyle](../properties/hierarchyuniquenamestyle-element-assl.md), [ID](../properties/id-element-assl.md), [MemberUniqueNameStyle](../properties/memberuniquenamestyle-element-assl.md), [Name](../properties/name-element-assl.md), [Visible](../properties/visible-element-assl.md), [Translations](../collections/translations-element-assl.md)|  
|Derived elements|[Dimension](../objects/dimension-element-assl.md) ([Dimensions](../collections/dimensions-element-assl.md) collection of [Cube](../objects/cube-element-assl.md))|  
  
## Remarks  
 There is one **CubeDimension** for each dimension relationship on a **Cube**. The **CubeDimension** covers all the **MeasureGroups** of the cube.  
  
 A **CubeDimension** must include a [CubeHierarchy](cubehierarchy-data-type-assl.md) if the dimension has something specific to say about the hierarchy, including disabling the hierarchy (thereby, allowing selection of which hierarchies apply to a particular dimension usage), or making the hierarchy invisible.  
  
 Similarly, a **CubeDimension** must include a [CubeAttribute](cubeattribute-data-type-assl.md) only if the dimension has something specific to say about the attribute. (There is no way to select which attributes apply to a particular dimension usage, though attributes can be made invisible).  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.CubeDimension>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  

---
title: "MeasureGroups Element (ASSL) | Microsoft Docs"
description: Learn about the MeasureGroups collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# MeasureGroups Element (ASSL)

  Contains the collection of [MeasureGroup](../objects/measuregroup-element-assl.md) elements associated with the parent element.  
  
## Syntax  
  
```xml  
  
<Cube> <!-- or CubeBinding, Perspective -->  
   ...  
   <MeasureGroups>  
      <MeasureGroup>...</MeasureGroup> <!-- parent: Cube -->  
      <MeasureGroup xsi:type="MeasureGroupBinding">...</MeasureGroup> <!-- parent: CubeBinding -->  
      <MeasureGroup xsi:type="PerspectiveMeasureGroup">...</MeasureGroup> <!-- parent: Perspective -->  
   </MeasureGroups>  
   ...  
</Cube>  
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
|Parent elements|[Cube](../objects/cube-element-assl.md), [CubeBinding](../data-type/cubebinding-data-type-out-of-line-assl.md), [Perspective](../objects/perspective-element-assl.md)|  
|Child elements|See the table.|  
  
|Ancestor or Parent|Child Element|  
|------------------------|-------------------|  
|[Cube](../objects/cube-element-assl.md)|[MeasureGroup](../objects/measuregroup-element-assl.md)|  
|[CubeBinding](../data-type/cubebinding-data-type-out-of-line-assl.md)|[MeasureGroup](../objects/measuregroup-element-assl.md) of type [MeasureGroupBinding](../data-type/measuregroupbinding-data-type-assl.md)|  
|[Perspective](../objects/perspective-element-assl.md)|[MeasureGroup](../objects/measuregroup-element-assl.md) of type [PerspectiveMeasureGroup](../data-type/perspectivemeasuregroup-data-type-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MeasureGroupCollection> or <xref:Microsoft.AnalysisServices.PerspectiveMeasureGroupCollection>.  

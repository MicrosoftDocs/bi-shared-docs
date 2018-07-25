---
title: "PerspectiveMeasureGroup Data Type (ASSL) | Microsoft Docs"
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
# PerspectiveMeasureGroup Data Type (ASSL)

  Defines a primitive data type that represents information about a measure group in a [Perspective](../objects/perspective-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<PerspectiveMeasureGroup>  
   <MeasureGroupID>...</MeasureGroupID>  
   <Measures>...</Measures>  
   <Annotations>...</Annotations>  
</PerspectiveMeasureGroup>  
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
|Child elements|[Annotations](../collections/annotations-element-assl.md), [MeasureGroupID](../properties/measuregroupid-element-assl.md), [Measures](../collections/measures-element-assl.md)|  
|Derived elements|[MeasureGroup](../objects/measuregroup-element-assl.md) ([MeasureGroups](../collections/measuregroups-element-assl.md) collection of [Perspective](../objects/perspective-element-assl.md))|  
  
## Remarks  
 A measure group in a perspective has the same structure as a measure group in the underlying cube.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.PerspectiveMeasureGroup>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  

---
title: "Visible Element (ASSL) | Microsoft Docs"
ms.date: 5/8/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
---
# Visible Element (ASSL)

  Determines the visibility of the parent element.  
  
## Syntax  
  
```xml  
  
<CalculationProperty> <!-- or one of the elements listed below in the Element Relationships table -->  
  
   <Visible >...</Visible >  
  
</CalculationProperty>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Boolean|  
|Default value|True|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[CalculationProperty](../objects/calculationproperty-element-assl.md), [Cube](../objects/cube-element-assl.md), [CubeDimension](../data-type/cubedimension-data-type-assl.md), [CubeHierarchy](../data-type/cubehierarchy-data-type-assl.md), [Database](../objects/database-element-assl.md), [Measure](../objects/measure-element-assl.md), [MemberProperty](../objects/attributerelationship-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The **Visible** element determines whether user interface components should display the parent element.  
  
 The elements that correspond to the parents of **Visible** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.CalculationProperty>, <xref:Microsoft.AnalysisServices.Cube>, <xref:Microsoft.AnalysisServices.CubeDimension>, <xref:Microsoft.AnalysisServices.CubeHierarchy>, <xref:Microsoft.AnalysisServices.Database>, and <xref:Microsoft.AnalysisServices.Measure>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

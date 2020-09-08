---
title: "DefaultMeasure Element (ASSL) | Microsoft Docs"
description: Learn about the DefaultMeasure property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# DefaultMeasure Element (ASSL)

  Contains a Multidimensional Expressions (MDX) expression that defines the default measure for a [Cube](../objects/cube-element-assl.md) or [Perspective](../objects/perspective-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Cube> <!-- or Perspective -->  
   ...  
   <DefaultMeasure>...</DefaultMeasure>  
   ...  
</Cube>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[Cube](../objects/cube-element-assl.md), [Perspective](../objects/perspective-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The elements that correspond to the parents of **DefaultMeasure** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.Cube> and <xref:Microsoft.AnalysisServices.Perspective>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

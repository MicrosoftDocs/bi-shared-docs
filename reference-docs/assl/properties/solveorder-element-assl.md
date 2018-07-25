---
title: "SolveOrder Element (ASSL) | Microsoft Docs"
ms.date: 7/25/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
---
# SolveOrder Element (ASSL)

  Indicates the solve order in which the [CalculationProperty](objects/calculationproperty-element-assl.md) element is applied to a calculated member or calculated cell definition.  
  
## Syntax  
  
```xml  
  
<CalculationProperty>  
   ...  
   <SolveOrder>...</SolveOrder>  
   ...  
</CalculationProperty>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Integer|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[CalculationProperty](objects/calculationproperty-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The **SolveOrder** property applies to **CalculationProperty** elements with a [CalculationType](properties/calculationtype-element-assl.md) of *Member* or *Cells*.  
  
 The element that corresponds to the parent of **SolveOrder** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.CalculationProperty>.  
  
## See Also  
 [CalculationProperties Element &#40;ASSL&#41;](collections/calculationproperties-element-assl.md)   
 [MdxScript Element &#40;ASSL&#41;](objects/mdxscript-element-assl.md)   
 [MdxScripts Element &#40;ASSL&#41;](collections/mdxscripts-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties/properties-assl.md)  
  
  

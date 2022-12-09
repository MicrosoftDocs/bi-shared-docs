---
title: "AssociatedMeasureGroupID Element (ASSL) | Microsoft Docs"
description: Learn about the AssociatedMeasureGroupID property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# AssociatedMeasureGroupID Element (ASSL)

  Contains the ID of the [MeasureGroup](../objects/measuregroup-element-assl.md) element associated with a [CalculationProperty](../objects/calculationproperty-element-assl.md) element or a [Kpi](../objects/kpi-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<CalculationProperty> <!-- or Kpi -->  
   ...  
   <AssociatedMeasureGroupID>...</AssociatedMeasureGroupID>  
   ...  
</CalculationProperty>  
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
|Parent element|[CalculationProperty](../objects/calculationproperty-element-assl.md), [Kpi](../objects/kpi-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 When applied to **CalculationProperty** elements, the **AssociatedMeasureGroupID** property applies to elements with a [CalculationType](calculationtype-element-assl.md) of *Member*.  
  
 The elements that correspond to the parents of **AssociatedMeasureGroupID** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.CalculationProperty> and <xref:Microsoft.AnalysisServices.Kpi>.  
  
## See Also  
 [CalculationProperties Element &#40;ASSL&#41;](../collections/calculationproperties-element-assl.md)   
 [MdxScript Element &#40;ASSL&#41;](../objects/mdxscript-element-assl.md)   
 [MdxScripts Element &#40;ASSL&#41;](../collections/mdxscripts-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

---
title: "DisplayFolder Element (ASSL) | Microsoft Docs"
description: Learn about the DisplayFolder property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# DisplayFolder Element (ASSL)

  Specifies the folder in which to list the parent element. Analysis Services applications for developers and administrators may support the use of display folders to categorize multiple elements visually.  
  
## Syntax  
  
```xml  
  
<CalculationProperty> <!-- or Hierarchy, Kpi, Measure, Translation -->  
   ...  
   <DisplayFolder>...</DisplayFolder>  
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
|Parent elements|[CalculationProperty](../objects/calculationproperty-element-assl.md), [Hierarchy](../objects/hierarchy-element-assl.md), [Kpi](../objects/kpi-element-assl.md), [Measure](../objects/measure-element-assl.md), [Translation](../objects/translation-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 In larger cubes, there may be hundreds of measures and hierarchies. The **DisplayFolder** property defines user appearance on the client. The value of the **DisplayFolder** property can contain any one of the following options:  
  
-   Be empty, denoting that the measure does not belong to a folder.  
  
-   Contain a single folder name, denoting that the measure should be rendered as belonging to a folder with the same name.  
  
-   Contain multiple folder names separated by a backslash (\\), denoting an embedded folder hierarchy.  
  
 The **DisplayFolder** property applies to **CalculationProperty** elements only if the value of [CalculationType](calculationtype-element-assl.md) is set to *Member*.  
  
 The elements that correspond to the parents of **DisplayFolder** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.CalculationProperty>, <xref:Microsoft.AnalysisServices.Hierarchy>, <xref:Microsoft.AnalysisServices.Kpi>, <xref:Microsoft.AnalysisServices.Measure>, and <xref:Microsoft.AnalysisServices.Translation>.  
  
## See Also  
 [CalculationProperties Element &#40;ASSL&#41;](../collections/calculationproperties-element-assl.md)   
 [MdxScript Element &#40;ASSL&#41;](../objects/mdxscript-element-assl.md)   
 [MdxScripts Element &#40;ASSL&#41;](../collections/mdxscripts-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

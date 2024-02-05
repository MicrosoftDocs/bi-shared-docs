---
title: "MeasureQualificaton Element (ASSL) | Microsoft Docs"
description: Learn about the MeasureQualificaton property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 09/14/2020
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# MeasureQualificaton Element (ASSL)

  Determines whether a prefix is applied to measures in the [MeasureGroup](../objects/measuregroup-element-assl.md).  
  
## Syntax  
  
```xml  
  
<MeasureGroup>  
   ...  
   <MeasureQualification>...</MeasureQualification>  
   ...  
</MeasureGroup>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*None*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[MeasureGroup](../objects/measuregroup-element-assl.md)|  
|Child elements|None|  
  
## Remarks

 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*None*|No prefix is applied to measures within this measure group.|  
|*PrefixMeasureGroup*|The unique name and caption of each measure in this measure group is prefixed by the name of the measure group and a single space.|  

 The element that corresponds to the parent of **MeasureQualification** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MeasureGroup>.  
  
## See Also

 [Cube Element &#40;ASSL&#41;](../objects/cube-element-assl.md)   
 [Dimension Element &#40;ASSL&#41;](../objects/dimension-element-assl.md)   
 [MeasureGroup Element &#40;ASSL&#41;](../objects/measuregroup-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
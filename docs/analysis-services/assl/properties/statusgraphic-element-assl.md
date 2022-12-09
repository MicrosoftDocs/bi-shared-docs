---
title: "StatusGraphic Element (ASSL) | Microsoft Docs"
description: Learn about the StatusGraphic property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: owend

ms.topic: reference
author: minewiskan
ms.author: owend

---
# StatusGraphic Element (ASSL)

  Contains the recommended graphical representation of the status of the [Kpi](../objects/kpi-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Kpi>  
   ...  
   <StatusGraphic>...</StatusGraphic>  
   ...  
</Kpi>  
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
|Parent element|[Kpi](../objects/kpi-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Traffic Light - Single*|Traffic light (single)|  
|*Traffic Light - Multiple*|Traffic light (multiple)|  
|*Road Signs*|Road signs|  
|*Gauge - Ascending*|Gauge|  
|*Gauge - Descending*|Reversed Gauge|  
|*Thermometer*|Thermometer|  
|*Cylinder*|Cylinder|  
|*Smiley Face*|Face|  
  
 The element that corresponds to the parent of **StatusGraphic** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Kpi>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

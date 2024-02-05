---
title: "Trend Element (ASSL) | Microsoft Docs"
description: Learn about the Trend property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# Trend Element (ASSL)

  Contains a Multidimensional Expressions (MDX) expression that returns a trend indicator for a [Kpi](../objects/kpi-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Kpi>  
   ...  
   <Trend>...</Trend>  
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
 The **Trend** element contains an MDX expression that evaluates to a number between -1 and 1.  
  
 The element that corresponds to the parent of **Trend** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Kpi>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

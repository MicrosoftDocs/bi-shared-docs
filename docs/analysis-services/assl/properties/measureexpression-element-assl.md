---
title: "MeasureExpression Element (ASSL) | Microsoft Docs"
description: Learn about the MeasureExpression property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: eur

ms.topic: reference
author: eric-urban
ms.author: eur

---
# MeasureExpression Element (ASSL)

  Contains the Multidimensional Expressions (MDX) expression that defines how the values of parent measure are obtained.  
  
## Syntax  
  
```xml  
  
<Measure>  
   ...  
   <MeasureExpression>...</MeasureExpression>  
   ...  
</Measure>  
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
|Parent element|[Measure](../objects/measure-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **MeasureExpression** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Measure>.  

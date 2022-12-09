---
title: "AggregationInstanceMeasure Data Type (ASSL) | Microsoft Docs"
description: Learn about the AggregationInstanceMeasure data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# AggregationInstanceMeasure Data Type (ASSL)

  Defines a primitive data type that represents information about a measure used by an aggregation instance.  
  
## Syntax  
  
```xml  
  
<AggregationInstanceMeasure>  
   <MeasureID>...</MeasureID>  
   <Source>...</Source>  
</AggregationInstanceMeasure>  
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
|Child elements|[MeasureID](../properties/measureid-element-assl.md), [Source](../properties/source-element-binding-assl.md)|  
|Derived elements|[Measure](../objects/measure-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.AggregationInstanceMeasure>.  

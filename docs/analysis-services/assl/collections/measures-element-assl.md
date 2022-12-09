---
title: "Measures Element (ASSL) | Microsoft Docs"
description: Learn about the Measures collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Measures Element (ASSL)

  Contains the collection of [Measure](../objects/measure-element-assl.md) elements associated with the parent element.  
  
## Syntax  
  
```xml  
  
<MeasureGroup> <!-- or AggregationInstance, MeasureGroupBinding (out-of-line), PerspectiveMeasureGroup -->  
   ...  
   <Measures>  
      <Measure>...</Measure>  
   </Measures>  
   ...  
</MeasureGroup>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[AggregationInstance](../objects/aggregationinstance-element-assl.md), [MeasureGroup](../objects/measuregroup-element-assl.md), [MeasureGroupBinding (out-of-line)](../data-type/measuregroupbinding-data-type-out-of-line-assl.md), [PerspectiveMeasureGroup](../data-type/perspectivemeasuregroup-data-type-assl.md)|  
|Child elements|[Measure](../objects/measure-element-assl.md)|  
  
## Remarks  
 The corresponding elements in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.MeasureCollection> and <xref:Microsoft.AnalysisServices.PerspectiveMeasureCollection>.  

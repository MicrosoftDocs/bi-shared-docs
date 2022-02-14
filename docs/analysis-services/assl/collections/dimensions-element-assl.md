---
title: "Dimensions Element (ASSL) | Microsoft Docs"
description: Learn about the Dimensions collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Dimensions Element (ASSL)

  Contains the collection of dimensions associated with the parent element.  
  
## Syntax  
  
```xml  
  
<Database> <!-- or Aggregation, AggregationDesign, AggregationInstance, Cube, MeasureGroup, Perspective -->  
   ...  
   <Dimensions>  
      <Dimension>...</Dimension>  
   </Dimensions>  
   ...  
</Database>  
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
|Parent elements|[Aggregation](../objects/aggregation-element-assl.md), [AggregationDesign](../objects/aggregationdesign-element-assl.md), [AggregationInstance](../objects/aggregationinstance-element-assl.md), [Cube](../objects/cube-element-assl.md), [Database](../objects/database-element-assl.md), [MeasureGroup](../objects/measuregroup-element-assl.md), [Perspective](../objects/perspective-element-assl.md)|  
|Child elements|[Dimension](../objects/dimension-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.DimensionCollection>.  

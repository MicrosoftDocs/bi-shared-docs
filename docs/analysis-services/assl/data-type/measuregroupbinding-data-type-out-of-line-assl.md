---
title: "MeasureGroupBinding Data Type (out-of-line) (ASSL) | Microsoft Docs"
description: Learn about the MeasureGroupBinding data type out-of-line element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# MeasureGroupBinding Data Type (out-of-line) (ASSL)

  Defines a primitive data type that represents a binding to a measure group.  
  
## Syntax  
  
```xml  
  
<MeasureGroupBinding>  
   <ID>...</ID>  
   <Source>...</Source>  
   <EstimatedRows>...</EstimatedRows>  
   <Dimensions>...</Dimensions>  
   <Measures>...</Measures>  
      <Partitions>...</Partitions>  
</MeasureGroupBinding>  
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
|Child elements|[Dimensions](../collections/dimensions-element-assl.md), [EstimatedRows](../properties/estimatedrows-element-assl.md), [ID](../properties/id-element-assl.md), [Measures](../collections/measures-element-assl.md), [Partitions](../collections/partitions-element-assl.md), [Source](../properties/source-element-binding-assl.md)|  
|Derived elements|See [Binding](binding-data-type-assl.md)|  
  
## Remarks  

---
title: "AggregationInstanceCubeDimension Data Type (ASSL) | Microsoft Docs"
ms.date: 07/25/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# AggregationInstanceCubeDimension Data Type (ASSL)

  Defines a primitive data type that represents information about a cube dimension used by an aggregation instance.  
  
## Syntax  
  
```xml  
  
<AggregationInstanceCubeDimension>  
   <CubeDimensionID>...</CubeDimensionID>  
   <KeyColumns>...</KeyColumns>  
   <Attributes>...</Attributes>  
</AggregationInstanceCubeDimension>  
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
|Child elements|[Attributes](../collections/attributes-element-assl.md), [CubeDimensionID](../properties/cubedimensionid-element-assl.md), [KeyColumns](../collections/keycolumns-element-assl.md)|  
|Derived elements|[Dimension](../objects/dimension-element-assl.md)|  
  
## Remarks  

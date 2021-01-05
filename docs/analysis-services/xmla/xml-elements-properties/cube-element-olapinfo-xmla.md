---
title: "Cube Element (OlapInfo) (XMLA) | Microsoft Docs"
description: Learn how the Cube element (OlapInfo) contains information about a cube for the parent CubeInfo element.
ms.date: 01/05/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Cube Element (OlapInfo) (XMLA)

  Contains information about a cube for the parent [CubeInfo](../xml-elements-properties/cubeinfo-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<CubeInfo>  
   <Cube>  
      <CubeName>...</CubeName>  
      <LastDataUpdate>...</LastDataUpdate>  
      <LastSchemaUpdate>...</LastSchemaUpdate>  
   </Cube>  
   ...  
</CubeInfo>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[CubeInfo](../xml-elements-properties/cubeinfo-element-xmla.md)|  
|Child elements|[CubeName](../xml-elements-properties/cubename-element-xmla.md), [LastDataUpdate](../xml-elements-properties/lastdataupdate-element-xmla.md), [LastSchemaUpdate](../xml-elements-properties/lastschemaupdate-element-xmla.md)|  
  
## Remarks  

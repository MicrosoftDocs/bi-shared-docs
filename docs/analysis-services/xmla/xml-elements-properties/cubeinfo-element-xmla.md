---
title: "CubeInfo Element (XMLA) | Microsoft Docs"
description: Learn how the CubeInfo element contains the cube metadata contained by the parent OlapInfo element.
ms.date: 01/05/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# CubeInfo Element (XMLA)

  Contains the cube metadata contained by the parent [OlapInfo](../xml-elements-properties/olapinfo-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<OlapInfo>  
   ...  
   <CubeInfo>  
      <Cube>...</Cube>  
   </CubeInfo>  
   ...  
</OlapInfo>  
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
|Parent elements|[OlapInfo](../xml-elements-properties/olapinfo-element-xmla.md)|  
|Child elements|[Cube](../xml-elements-properties/cube-element-olapinfo-xmla.md)|  
  
## Remarks  
 The **CubeInfo** element contains one **Cube** element for each cube referenced in the multidimensional dataset.  
  
> [!NOTE]  
>  Analysis Services returns only a single **Cube** element in this collection because Analysis Services does not support statements that reference multiple cubes in the FROM clause of the Multidimensional Expressions (MDX) language.  

---
title: "OlapInfo Element (XMLA) | Microsoft Docs"
description: Learn how the OlapInfo element contains the axis and cell metadata contained by a root element that uses the MDDataSet data type.
ms.date: 07/24/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# OlapInfo Element (XMLA)

  Contains the axis and cell metadata contained by a [root](../xml-elements-properties/root-element-xmla.md) element that uses the [MDDataSet](../xml-data-types/mddataset-data-type-xmla.md) data type.  
  
## Syntax  
  
```xml  
  
<root xmlns="urn:schemas-microsoft-com:xml-analysis:mddataset">  
   ...  
   <OlapInfo>  
      <CubeInfo>...</CubeInfo>  
      <AxesInfo>...</AxesInfo>  
      <CellInfo>...</CellInfo>  
   </OlapInfo>  
   ...  
</root>  
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
|Parent elements|[root](../xml-elements-properties/root-element-xmla.md)|  
|Child elements|[AxesInfo](../xml-elements-properties/axesinfo-element-xmla.md), [CellInfo](../xml-elements-properties/cellinfo-element-xmla.md), [CubeInfo](../xml-elements-properties/cubeinfo-element-xmla.md)|  
  
## Remarks  
 The **OLAPInfo** section of a **root** element using the **MDDataSet** data type provides metadata about the cube, the axes of the multidimensional result, and the properties of the cells included the result.  

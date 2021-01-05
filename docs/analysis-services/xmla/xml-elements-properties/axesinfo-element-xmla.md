---
title: "AxesInfo Element (XMLA) | Microsoft Docs"
description: Learn how the AxesInfo element contains a collection of AxisInfo elements, representing the axis metadata contained by the parent OlapInfo element.
ms.date: 01/05/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# AxesInfo Element (XMLA)

  Contains a collection of [AxisInfo](../xml-elements-properties/axisinfo-element-xmla.md) elements, representing the axis metadata contained by the parent [OlapInfo](../xml-elements-properties/olapinfo-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<OlapInfo>  
   ...  
   <AxesInfo>  
      <AxisInfo>...</AxisInfo>  
   </AxesInfo>  
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
|Child elements|[AxisInfo](../xml-elements-properties/axisinfo-element-xmla.md)|  
  
## Remarks  
 The **AxesInfo** element contains one **AxisInfo** element for each axis within the multidimensional dataset returned by a **root** element using the **MDDataSet** data type.  
  
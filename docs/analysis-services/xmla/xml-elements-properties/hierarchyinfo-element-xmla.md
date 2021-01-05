---
title: "HierarchyInfo Element (XMLA) | Microsoft Docs"
description: Learn how the HierarchyInfo element represents a single hierarchy contained by a parent AxisInfo element.
ms.date: 01/05/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# HierarchyInfo Element (XMLA)

  Represents a single hierarchy contained by a parent [AxisInfo](../xml-elements-properties/axisinfo-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<AxisInfo>  
   ...  
   <HierarchyInfo name="string">  
      <UName>...</UName>  
      <Caption>...</Caption>  
      <LName>...</LName>  
      <LNum>...</LNum>  
      <DisplayInfo>...</DisplayInfo>  
   </HierarchyInfo>  
   ...  
</AxisInfo>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[AxisInfo](../xml-elements-properties/axisinfo-element-xmla.md)|  
|Child elements|[Caption](../xml-elements-properties/caption-element-xmla.md), [DisplayInfo](../xml-elements-properties/displayinfo-element-xmla.md), [LName](../xml-elements-properties/lname-element-xmla.md), [LNum](../xml-elements-properties/lnum-element-xmla.md), [UName](../xml-elements-properties/uname-element-xmla.md)|  
  
## Attributes  
  
|Attribute|Description|  
|---------------|-----------------|  
|Name|Required **String** attribute. The name of the hierarchy.|  
  
## Remarks  

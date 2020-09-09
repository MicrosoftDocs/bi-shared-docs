---
title: "LastDataUpdate Element (XMLA) | Microsoft Docs"
description: Learn how the LastDataUpdate element contains the date and time that the data of the cube represented by the parent Cube element was last updated.
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
# LastDataUpdate Element (XMLA)

  Contains the date and time that the data of the cube represented by the parent [Cube](../xml-elements-properties/cube-element-olapinfo-xmla.md) element was last updated.  
  
## Syntax  
  
```xml  
  
<Cube>  
   ...  
   <LastDataUpdate>...</LastDataUpdate>  
   ...  
</Cube>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|dateTime|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Cube](../xml-elements-properties/cube-element-olapinfo-xmla.md)|  
|Child elements|None|  
  
## Remarks  

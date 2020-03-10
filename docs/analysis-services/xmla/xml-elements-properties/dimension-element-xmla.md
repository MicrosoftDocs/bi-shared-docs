---
title: "Dimension Element (XMLA) | Microsoft Docs"
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
# Dimension Element (XMLA)

  Identifies the cube dimension represented by the parent [Object](../xml-elements-properties/object-element-dimension-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<Object>  
   ...  
   <Dimension>...</Dimension>  
   ...  
</Object>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Object](../xml-elements-properties/object-element-dimension-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **Dimension** element is an object identifier that contains the name of the cube dimension represented by the **Object** element.  

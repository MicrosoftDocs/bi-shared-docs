---
title: "CustomRollup Element (XMLA) | Microsoft Docs"
description: Learn how the CustomRollup element contains the custom rollup formula for an attribute member represented by the parent Attribute element.
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
# CustomRollup Element (XMLA)

  Contains the custom rollup formula for an attribute member represented by the parent [Attribute](../xml-elements-properties/attribute-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<Attribute>  
   ...  
   <CustomRollup>...</CustomRollup>  
   ...  
</Attribute>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Attribute](../xml-elements-properties/attribute-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **CustomRollup** element contains a Multidimensional Expressions (MDX) expression that defines the rollup behavior of the attribute member defined by the parent **Attribute** element.  
  
 
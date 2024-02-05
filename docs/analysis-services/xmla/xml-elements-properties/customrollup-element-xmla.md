---
title: "CustomRollup Element (XMLA) | Microsoft Docs"
description: Learn how the CustomRollup element contains the custom rollup formula for an attribute member represented by the parent Attribute element.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

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
  
 
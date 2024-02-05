---
title: "UnaryOperator Element (XMLA) | Microsoft Docs"
description: Learn how the UnaryOperator element contains the unary operator for an attribute member represented by the parent Attribute element.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# UnaryOperator Element (XMLA)

  Contains the unary operator for an attribute member represented by the parent [Attribute](../xml-elements-properties/attribute-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<Attribute>  
   ...  
   <UnaryOperator>...</UnaryOperator>  
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
 The **UnaryOperator** element contains a Multidimensional Expressions (MDX) expression that defines the unary operator for the attribute member defined by the parent **Attribute** element.  

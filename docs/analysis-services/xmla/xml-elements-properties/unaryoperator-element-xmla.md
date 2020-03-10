---
title: "UnaryOperator Element (XMLA) | Microsoft Docs"
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

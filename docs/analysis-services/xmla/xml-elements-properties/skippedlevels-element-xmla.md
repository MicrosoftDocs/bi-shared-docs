---
title: "SkippedLevels Element (XMLA) | Microsoft Docs"
description: Learn how the SkippedLevels element contains the number of levels skipped by an attribute member represented by the parent [Attribute](../xml-elements-properties/attribute-element-xmla.md) element.
ms.date: 01/05/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# SkippedLevels Element (XMLA)

  Contains the number of levels skipped by an attribute member represented by the parent [Attribute](../xml-elements-properties/attribute-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<Attribute>  
   ...  
   <SkippedLevels>...</SkippedLevels>  
   ...  
</Attribute>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Integer|  
|Default value|0|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Attribute](../xml-elements-properties/attribute-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **SkippedLevels** element determines the number of levels skipped by an attribute member defined by the parent **Attribute** element.  

---
title: "MoveWithDescendants Element (XMLA) | Microsoft Docs"
description: Learn how the MoveWithDescendants element indicates whether the descendants of attribute members are also updated by the parent Update command.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# MoveWithDescendants Element (XMLA)

  Indicates whether the descendants of attribute members are also updated by the parent [Update](../xml-elements-commands/update-element-xmla.md) command.  
  
## Syntax  
  
```xml  
  
<Update>  
   ...  
   <MoveWithDescendants>...</MoveWithDescendants>  
   ...  
</Update>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Boolean|  
|Default value|False|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Update](../xml-elements-commands/update-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **MoveWithDescendants** element determines whether the **Update** command should not just update the attribute members identified by the [Attributes](../xml-elements-properties/attributes-element-xmla.md) element, but also that the descendants of those attribute members are to be updated as well.  
  
> [!NOTE]  
>  This element applies only to attribute members in parent-child hierarchies.  

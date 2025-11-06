---
title: "Update Element (XMLA) | Microsoft Docs"
description: Learn how the Update element updates attribute members in a dimension.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference

---
# Update Element (XMLA)

  Updates attribute members in a dimension.  
  
## Syntax  
  
```xml  
  
<Command>  
   <Update>  
      <Object>...</Object>  
      <MoveWithDescendants>...</MoveWithDescendants>  
      <Attributes>...</Attributes>  
      <Where>...</Where>  
   </Update>  
</Command>  
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
|Parent elements|[Command](../xml-elements-properties/command-element-xmla.md)|  
|Child elements|[Attributes](../xml-elements-properties/attributes-element-xmla.md), [MoveWithDescendants](../xml-elements-properties/movewithdescendants-element-xmla.md), [Object](../xml-elements-properties/object-element-dimension-xmla.md), [Where](../xml-elements-properties/where-element-xmla.md)|  
  
## Remarks  
 The **Update** command moves attribute members within a write-enabled dimension.  

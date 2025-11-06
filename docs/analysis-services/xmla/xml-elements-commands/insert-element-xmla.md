---
title: "Insert Element (XMLA) | Microsoft Docs"
description: Learn how the Insert element inserts attribute members into a dimension.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference

---
# Insert Element (XMLA)

  Inserts attribute members into a dimension.  
  
## Syntax  
  
```xml  
  
<Command>  
   <Insert>  
      <Object>...</Object>  
      <Attributes>...</Attributes>  
   </Insert>  
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
|Child elements|[Attributes](../xml-elements-properties/attributes-element-xmla.md), [Object](../xml-elements-properties/object-element-dimension-xmla.md)|  
  
## Remarks  
 The **Insert** command inserts new attribute members into a write-enabled dimension.  

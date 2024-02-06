---
title: "Drop Element (XMLA) | Microsoft Docs"
description: Learn how the Drop element deletes attribute members from a dimension.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Drop Element (XMLA)

  Deletes attribute members from a dimension.  
  
## Syntax  
  
```xml  
  
<Command>  
   <Drop>  
      <Object>...</Object>  
      <DeleteWithDescendants>...</DeleteWithDescendants>  
      <Where>...</Where>  
   </Drop>  
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
|Child elements|[DeleteWithDescendants](../xml-elements-properties/deletewithdescendants-element-xmla.md), [Object](../xml-elements-properties/object-element-dimension-xmla.md), [Where](../xml-elements-properties/where-element-xmla.md)|  
  
## Remarks  
 The **Drop** command deletes attribute members from a write-enabled dimension.  
  
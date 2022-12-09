---
title: "UpdateCells Element (XMLA) | Microsoft Docs"
description: Learn how the UpdateCells element updates cells in a write-enabled cube.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
---
# UpdateCells Element (XMLA)

  Updates cells in a write-enabled cube.  
  
## Syntax  
  
```xml  
  
<Command>  
   <UpdateCells>  
      <Cell>...</Cell>  
   </UpdateCells>  
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
|Child elements|[Cell](../xml-elements-properties/cell-element-xmla.md)|  
  
## Remarks  
 The **UpdateCells** command updates cells in a cube that supports cell writeback.  

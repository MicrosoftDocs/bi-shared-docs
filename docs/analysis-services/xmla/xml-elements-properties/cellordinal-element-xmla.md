---
title: "CellOrdinal Element (XMLA) | Microsoft Docs"
description: Learn how the CellOrdinal element contains the ordinal position within a cube of a cell to be updated by an UpdateCells command.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# CellOrdinal Element (XMLA)

  Contains the ordinal position within a cube of a cell to be updated by an [UpdateCells](../xml-elements-commands/updatecells-element-xmla.md) command.  
  
## Syntax  
  
```xml  
  
<Cell>  
   ...  
   <CellOrdinal>...</CellOrdinal>  
   ...  
</Cell>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Long|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Cell](../xml-elements-properties/cell-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **CellOrdinal** element identifies the cell to be updated by the **UpdateCells** command.  

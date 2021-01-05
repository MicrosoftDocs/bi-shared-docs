---
title: "Cell Element (XMLA) | Microsoft Docs"
description: Learn how the Cell element contains information about a cell to be updated by an UpdateCells command.
ms.date: 01/05/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Cell Element (XMLA)

  Contains information about a cell to be updated by an [UpdateCells](../xml-elements-commands/updatecells-element-xmla.md) command.  
  
## Syntax  
  
```xml  
  
<UpdateCells>  
   ...  
   <Cell CellOrdinal="Long">  
      <Value>...</Value>  
   </Cell>  
   ...  
</UpdateCells>  
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
|Parent elements|[UpdateCells](../xml-elements-commands/updatecells-element-xmla.md)|  
|Child elements|[Value](../xml-elements-properties/value-element-xmla.md)|  
  
## Attributes  
  
|Attribute|Description|  
|---------------|-----------------|  
|CellOrdinal|Required **Long** attribute. Contains the zero-based ordinal position of the cell to be updated.|  
  
## Remarks  

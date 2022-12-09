---
title: "Value Element (XMLA) | Microsoft Docs"
description: Learn how the Value element contains the desired value of an Attribute element to be added by an Insert command, or a Cell element to be updated by an UpdateCells command.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Value Element (XMLA)

  Contains the desired value of an [Attribute](../xml-elements-properties/attribute-element-xmla.md) element to be added by an [Insert](../xml-elements-commands/insert-element-xmla.md) command, or a [Cell](../xml-elements-properties/cell-element-xmla.md) element to be updated by an [UpdateCells](../xml-elements-commands/updatecells-element-xmla.md) command.  
  
## Syntax  
  
```xml  
  
<Attribute> <!-- or Cell --!>  
   ...  
   <Value>...</Value>  
   ...  
</Attribute>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Any|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Attribute](../xml-elements-properties/attribute-element-xmla.md), [Cell](../xml-elements-properties/cell-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 For **Attribute** elements, the **Value** element contains the desired value that the member should contain after the **Insert** command is committed. 
  
 For **Cell** elements, the **Value** element contains the desired value that the cell should contain after the **UpdateCells** command is committed. The actual value stored in the writeback table for that cell is the difference between the original value of the cell and the desired value of the cell.  
  
 The data type used by this element should match the data type of the cell to be updated.
 
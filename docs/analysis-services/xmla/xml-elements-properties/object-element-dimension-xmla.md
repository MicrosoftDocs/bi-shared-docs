---
title: "Object Element (Dimension) (XMLA) | Microsoft Docs"
description: Learn how the Object element (dimension) contains an object reference for the dimension on which the parent Insert, Update, or Drop command is executed.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Object Element (Dimension) (XMLA)

  Contains an object reference for the dimension on which the parent [Insert](../xml-elements-commands/insert-element-xmla.md), [Update](../xml-elements-commands/update-element-xmla.md), or [Drop](../xml-elements-commands/drop-element-xmla.md) command is executed.  
  
## Syntax  
  
```xml  
  
<Insert> <!-- or any of the parent elements in the Element relationships table -->  
...  
   <Object>  
      <Database>...</Database>  
      <Cube>...</Cube>  
      <Dimension>...</Dimension>  
   </Object>  
...  
</Insert>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Drop](../xml-elements-commands/drop-element-xmla.md), [Insert](../xml-elements-commands/insert-element-xmla.md), [Update](../xml-elements-commands/update-element-xmla.md)|  
|Child elements|[Cube](../xml-elements-properties/cube-element-xmla.md), [Database](../xml-elements-properties/database-element-xmla.md), [Dimension](../xml-elements-properties/dimension-element-xmla.md)|  
  
## Remarks  
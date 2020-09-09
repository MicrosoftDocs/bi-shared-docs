---
title: "ClearCache Element (XMLA) | Microsoft Docs"
description: Learn how the ClearCache element clears the memory cache for the specified object on a Analysis Services instance.
ms.date: 07/24/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# ClearCache Element (XMLA)

  Clears the memory cache for the specified object on a Analysis Services instance.  
  
## Syntax  
  
```xml  
  
<Command>  
   <ClearCache>  
      <Object>...</Object>  
   </ClearCache>  
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
|Child elements|[Object](../xml-elements-properties/object-element-xmla.md)|  
  
## Remarks  
 The **ClearCache** command flushes the cache for a specified database, dimension, cube, measure group, or partition on an Analysis Services instance. If an object other than a database, dimension, cube, measure group, or partition is specified in the **Object** element, an error occurs.  
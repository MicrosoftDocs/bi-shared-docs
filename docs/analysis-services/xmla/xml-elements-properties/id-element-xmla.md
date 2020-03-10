---
title: "ID Element (XMLA) | Microsoft Docs"
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
# ID Element (XMLA)

  Identifies a lock on which to execute the parent [Lock](../xml-elements-commands/lock-element-xmla.md) or [Unlock](../xml-elements-commands/unlock-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<Lock> <!-- or Unlock>  
   ...  
   <ID>...</ID>  
   ...  
</Lock>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Lock](../xml-elements-commands/lock-element-xmla.md), [Unlock](../xml-elements-commands/unlock-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **ID** element contains a globally unique identifier (GUID) used to identify a lock.  

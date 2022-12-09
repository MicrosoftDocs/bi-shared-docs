---
title: "SessionID Element (XMLA) | Microsoft Docs"
description: Learn how the SessionID element identifies an active session on which to execute the parent Cancel element.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# SessionID Element (XMLA)

  Identifies an active session on which to execute the parent [Cancel](../xml-elements-commands/cancel-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<Cancel>  
   ...  
   <SessionID>...</SessionID>  
   ...  
</Cancel>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Cancel](../xml-elements-commands/cancel-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
  
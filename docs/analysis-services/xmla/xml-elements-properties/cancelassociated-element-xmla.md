---
title: "CancelAssociated Element (XMLA) | Microsoft Docs"
description: Learn how the CancelAssociated element indicates whether the parent Cancel element should cancel all associated commands.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# CancelAssociated Element (XMLA)

  Indicates whether the parent [Cancel](../xml-elements-commands/cancel-element-xmla.md) element should cancel all associated commands.  
  
## Syntax  
  
```xml  
  
<Cancel>  
   ...  
   <ConnectionID>...</ConnectionID>  
   ...  
</Cancel>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Boolean|  
|Default value|False|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Cancel](../xml-elements-commands/cancel-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 If this element is specified and set to **True**, every corresponding connection, session, and command identified in the parent **Cancel** command is canceled.  
  

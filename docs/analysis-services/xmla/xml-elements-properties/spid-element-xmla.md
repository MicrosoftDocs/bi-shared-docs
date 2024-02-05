---
title: "SPID Element (XMLA) | Microsoft Docs"
description: Learn how the SPID element identifies an active server process identifier (SPID) on which to execute the parent Cancel element.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# SPID Element (XMLA)

  Identifies an active server process identifier (SPID) on which to execute the parent [Cancel](../xml-elements-commands/cancel-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<Cancel>  
   ...  
   <SPID>...</SPID>  
   ...  
</Cancel>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Integer|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Cancel](../xml-elements-commands/cancel-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **SPID** element represents the server process ID (SPID) used for a given session on an instance of Analysis Services.  
 
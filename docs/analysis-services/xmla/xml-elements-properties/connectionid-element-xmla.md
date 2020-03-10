---
title: "ConnectionID Element (XMLA) | Microsoft Docs"
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
# ConnectionID Element (XMLA)

  Identifies an active connection on which to execute the parent [Cancel](../xml-elements-commands/cancel-element-xmla.md) element.  
  
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
|Data type and length|Integer|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Cancel](../xml-elements-commands/cancel-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 
---
title: "Source Element (Error) (XMLA) | Microsoft Docs"
description: Learn how the Source element (error) contains the name of the component that generated the parent Error element.
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
# Source Element (Error) (XMLA)

  Contains the name of the component that generated the parent [Error](../xml-elements-properties/error-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<Error>  
   ...  
   <Source>...</Source>  
   ...  
</Error>  
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
|Parent elements|[Error](../xml-elements-properties/error-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  

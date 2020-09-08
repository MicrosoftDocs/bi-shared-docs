---
title: "Goal Element (ASSL) | Microsoft Docs"
description: Learn about the Goal property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
---
# Goal Element (ASSL)

  Identifies the desired goal in a [Kpi](../objects/kpi-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Kpi>  
   ...  
   <Goal>...</Goal>  
   ...  
</Kpi>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[Kpi](../objects/kpi-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The **Goal** element contains a Multidimensional Expressions (MDX) expression.  
  
 The element that corresponds to the parent of **Goal** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Kpi>.  

  

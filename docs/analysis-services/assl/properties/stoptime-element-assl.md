---
title: "StopTime Element (ASSL) | Microsoft Docs"
description: Learn about the StopTime property element in the Analysis Services Scripting Language (ASSL) schema.
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
# StopTime Element (ASSL)

  Specifies the date and time at which a [Trace](../objects/trace-element-assl.md) element should stop.  
  
## Syntax  
  
```xml  
  
<Trace>  
   ...  
   <StopTime>...</StopTime>  
   ...  
</Trace>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|DateTime|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[Trace](../objects/trace-element-assl.md)|  
|Child elements|None|  
  
 The element that corresponds to the parent of **StopTime** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Trace>.  
  
## See Also  
 [Traces Element &#40;ASSL&#41;](../collections/traces-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

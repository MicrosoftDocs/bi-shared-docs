---
title: "LogFileRollover Element (ASSL) | Microsoft Docs"
description: Learn about the LogFileRollover property element in the Analysis Services Scripting Language (ASSL) schema.
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
# LogFileRollover Element (ASSL)

  Specifies whether logging of [Trace](../objects/trace-element-assl.md) output should roll over to a new file or should stop when the maximum log file size that is specified in [LogFileSize](logfilesize-element-assl.md) is reached.  
  
## Syntax  
  
```xml  
  
<Trace>  
   ...  
   <LogFileRollover>...</LogFileRollover>  
   ...  
</Trace>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Boolean|  
|Default value|False|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[Trace](../objects/trace-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 If the value of the **LogFileRollover** element is set to True, a new file is started when the size of the log file exceeds the value that is specified in the **LogFileSize** element of the **Trace** parent element; otherwise, logging stops.  
  
 The element that corresponds to the parent of **LogFileRollover** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Trace>.  
  
## See Also  
 [Traces Element &#40;ASSL&#41;](../collections/traces-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

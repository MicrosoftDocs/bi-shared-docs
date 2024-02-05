---
title: "KeyErrorLimitAction Element (ASSL) | Microsoft Docs"
description: Learn about the KeyErrorLimitAction property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# KeyErrorLimitAction Element (ASSL)

  Specifies the action Analysis Services takes when the key error count that is specified in the [KeyErrorLimit](keyerrorlimit-element-assl.md) element is reached.  
  
## Syntax  
  
```xml  
  
<ErrorConfiguration>  
   ...  
      <KeyErrorLimitAction>...</KeyErrorLimitAction>  
   ...  
</ErrorConfiguration>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*StopProcessing*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[ErrorConfiguration](../objects/errorconfiguration-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*StopProcessing*|Stops processing the object.|  
|*StopLogging*|Continues processing the object, but stops logging errors that are encountered during processing.|  
  
 The enumeration that corresponds to the allowed values for **KeyErrorLimitAction** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.KeyErrorLimitAction>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

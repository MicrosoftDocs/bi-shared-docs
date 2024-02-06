---
title: "KeyErrorLogFile Element (ASSL) | Microsoft Docs"
description: Learn about the KeyErrorLogFile property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# KeyErrorLogFile Element (ASSL)

  Contains the file name for logging processing errors.  
  
## Syntax  
  
```xml  
  
<ErrorConfiguration>  
   ...  
      <KeyErrorLogFile>...</KeyErrorLogFile>  
   ...  
</ErrorConfiguration>  
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
|Parent element|[ErrorConfiguration](../objects/errorconfiguration-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **KeyErrorLogFile** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ErrorConfiguration>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

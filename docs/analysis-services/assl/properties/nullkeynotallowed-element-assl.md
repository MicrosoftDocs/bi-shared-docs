---
title: "NullKeyNotAllowed Element (ASSL) | Microsoft Docs"
description: Learn about the NullKeyNotAllowed property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# NullKeyNotAllowed Element (ASSL)

  Determines how the Analysis Services processing engine handles a null key error encountered during processing.  
  
## Syntax  
  
```xml  
  
<ErrorConfiguration>  
   ...  
   <NullKeyNotAllowed>...</NullKeyNotAllowed>  
   ...  
</ErrorConfiguration>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*ReportAndContinue*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[ErrorConfiguration](../objects/errorconfiguration-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 Null key errors occur when a null value is encountered in a key column in which null values are not allowed, forcing the record to be discarded during processing. However, this error occurs only if the [NullProcessing](nullprocessing-element-assl.md) element for the **DataItem** ancestor of the **ErrorConfiguration** parent element is set to *Error*.  
  
 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*IgnoreError*|Processing ignores the error and continues.|  
|*ReportAndContinue*|Processing reports the error and continues.|  
|*ReportAndStop*|Processing reports the error and stops.|  
  
 The enumeration that corresponds to the allowed values for **NullKeyNotAllowed** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ErrorOption>.  
  
## See Also  
 [ErrorConfiguration Element &#40;ASSL&#41;](../objects/errorconfiguration-element-assl.md)  
  
  

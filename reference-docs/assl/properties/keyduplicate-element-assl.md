---
title: "KeyDuplicate Element (ASSL) | Microsoft Docs"
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
# KeyDuplicate Element (ASSL)

  Determines how Analysis Services handles a duplicate key error if it encounters one during processing.  
  
## Syntax  
  
```xml  
  
<ErrorConfiguration>  
   ...  
      <KeyDuplicate>...</KeyDuplicate>  
   ...  
</ErrorConfiguration>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*IgnoreError*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[ErrorConfiguration](objects/errorconfiguration-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 Duplicate key errors are generated only during dimension processing, when an attribute key is encountered more than once. Because attribute keys must be unique,Analysis Services discards the duplicate records. Duplicate key errors typically indicate a flaw in the design of the dimension, specifically in the relationships between attributes.  
  
 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*IgnoreError*|Processing should ignore the error and continue.|  
|*ReportAndContinue*|Processing should report the error and continue.|  
|*ReportAndStop*|Processing should report the error and stop.|  
  
 The enumeration that corresponds to the allowed values for **KeyDuplicate** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ErrorOption>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties/properties-assl.md)  
  
  

---
title: "KeyNotFound Element (ASSL) | Microsoft Docs"
description: Learn about the KeyNotFound property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: eur

ms.topic: reference
author: eric-urban
ms.author: eur

---
# KeyNotFound Element (ASSL)

  Specifies how Analysis Services responds when it encounters a referential integrity error.  
  
## Syntax  
  
```xml  
  
<ErrorConfiguration>  
   ...  
      <KeyNotFound>...</KeyNotFound>  
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
 Referential integrity errors occur when a foreign key value in a dependent table does not have a corresponding entry in the parent table. This error occurs whenAnalysis Services processes a dimension in which the fact table references a foreign key value that does not exist in the dimension table for that dimension, or whenAnalysis Services processes a partition when the dimension main table for a dimension that is included in the partition references a key value that does not exist in another associated dimension table. (In the case of dimensions with parent-child hierarchies and parent attributes, this can also occur when the dimension main table for a dimension that is included in the partition references a key value that does not exist in the same dimension table.)  
  
 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*IgnoreError*|Processing should ignore the error and continue.|  
|*ReportAndContinue*|Processing should report the error and continue.|  
|*ReportAndStop*|Processing should report the error and stop.|  
  
 The enumeration that corresponds to the allowed values for **KeyNotFound** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ErrorOption>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

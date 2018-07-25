---
title: "ErrorConfiguration Element (ASSL) | Microsoft Docs"
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# ErrorConfiguration Element (ASSL)

  Specifies settings for handling errors that can occur when the parent element is processed.  
  
## Syntax  
  
```xml  
  
<Cube> <!-- or Dimension, MeasureGroup, MiningStructure, Partition -->  
   ...  
   <ErrorConfiguration>  
      <KeyErrorLimit>...</KeyErrorLimit>  
      <KeyErrorLogFile>...</KeyErrorLogFile>  
      <KeyErrorAction>...</KeyErrorAction>  
      <KeyErrorLimitAction>...</KeyErrorLimitAction>  
      <KeyNotFound>...</KeyNotFound>  
      <KeyDuplicate>...</KeyDuplicate>  
      <NullKeyConvertedToUnknown>...</NullKeyConvertedToUnknown>  
      <NullKeyNotAllowed>...<NullKeyNotAllowed>  
   </ErrorConfiguration>  
   ...  
</Cube >  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Cube](objects/cube-element-assl.md), [Dimension](objects/dimension-element-assl.md), [MeasureGroup](objects/measuregroup-element-assl.md), [MiningStructure](objects/miningstructure-element-assl.md), [Partition](objects/partition-element-assl.md)|  
|Child elements|[KeyDuplicate](properties/keyduplicate-element-assl.md), [KeyErrorAction](properties/keyerroraction-element-assl.md), [KeyErrorLimit](properties/keyerrorlimit-element-assl.md), [KeyErrorLimitAction](properties/keyerrorlimitaction-element-assl.md), [KeyErrorLogFile](properties/keyerrorlogfile-element-assl.md), [KeyNotFound](properties/keynotfound-element-assl.md), [NullKeyConvertedToUnknown](properties/nullkeyconvertedtounknown-element-assl.md), [NullKeyNotAllowed](properties/nullkeynotallowed-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ErrorConfiguration>.  
  
## See Also  
 [Objects &#40;ASSL&#41;](objects/objects-assl.md)  
  
  

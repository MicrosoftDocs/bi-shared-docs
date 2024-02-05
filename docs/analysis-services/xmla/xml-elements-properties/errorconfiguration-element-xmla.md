---
title: "ErrorConfiguration Element (XMLA) | Microsoft Docs"
description: Learn how the ErrorConfiguration element specifies settings for handling errors that can occur during a Batch or Process operation.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# ErrorConfiguration Element (XMLA)

  Specifies settings for handling errors that can occur during a [Batch](../xml-elements-commands/batch-element-xmla.md) or [Process](../xml-elements-commands/process-element-xmla.md) operation.  
  
## Syntax  
  
```xml  
  
<Batch> <!-- or Process -->  
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
</Batch>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Batch](../xml-elements-commands/batch-element-xmla.md), [Process](../xml-elements-commands/process-element-xmla.md)|  
|Child elements|[KeyDuplicate](../../assl/properties/keyduplicate-element-assl.md), [KeyErrorAction](../../assl/properties/keyerroraction-element-assl.md), [KeyErrorLimit](../../assl/properties/keyerrorlimit-element-assl.md), [KeyErrorLimitAction](../../assl/properties/keyerrorlimitaction-element-assl.md), [KeyErrorLogFile](../../assl/properties/keyerrorlogfile-element-assl.md), [KeyNotFound](../../assl/properties/keynotfound-element-assl.md), [NullKeyConvertedToUnknown](../../assl/properties/nullkeyconvertedtounknown-element-assl.md), [NullKeyNotAllowed](../../assl/properties/nullkeynotallowed-element-assl.md)|  
  
## Remarks  
 The structure of this element is identical to the structure of the **ErrorConfiguration** element in Analysis Services Scripting Language (ASSL).
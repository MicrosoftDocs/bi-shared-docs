---
title: "KeyErrorAction Element (ASSL) | Microsoft Docs"
description: Learn about the KeyErrorAction property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# KeyErrorAction Element (ASSL)

  Specifies the action for Analysis Services to take when an error occurs on a key.  
  
## Syntax  
  
```xml  
  
<ErrorConfiguration>  
   ...  
      <KeyErrorAction>...</KeyErrorAction>  
   ...  
</ErrorConfiguration>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*ConvertToUnknown*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[ErrorConfiguration](../objects/errorconfiguration-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*ConvertToUnknown*|Convert the problem key to the unknown member value.|  
|*DiscardRecord*|Discard the record.|  
  
 The enumeration that corresponds to the allowed values for **KeyErrorAction** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.KeyErrorAction>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

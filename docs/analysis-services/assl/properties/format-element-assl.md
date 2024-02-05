---
title: "Format Element (ASSL) | Microsoft Docs"
description: Learn about the Format property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# Format Element (ASSL)

  Contains the required format of the [DataItem](../data-type/dataitem-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<DataItem>  
   ...  
   <Format>...</Format>  
      ...  
</DataItem>  
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
|Parent element|[DataItem](../data-type/dataitem-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 Allowed values for the **Format** element are Microsoft Office Excel formats, and the strings *TrimRight*, *TrimLeft*, *TrimAll*, and *TrimNone*. For trimming, *TrimRight* is the default.  
  
 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|Any Excel format string|Data is formatted according to the specified named or custom format string. Any format string that Excel supports can be supplied.|  
|*TrimAll*|Data is trimmed on the left and right.|  
|*TrimLeft*|Data is trimmed on the left.|  
|*TrimNone*|Data is not trimmed.|  
|*TrimRight*|Data is trimmed on the right.|  
  
 The element that corresponds to the parent of **Format** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.DataItem>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

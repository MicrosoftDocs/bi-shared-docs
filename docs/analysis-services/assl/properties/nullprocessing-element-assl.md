---
title: "NullProcessing Element (ASSL) | Microsoft Docs"
description: Learn about the NullProcessing property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# NullProcessing Element (ASSL)

  Defines how null values are processed.  
  
## Syntax  
  
```xml  
  
<DataItem>  
   ...  
   <NullProcessing>...</NullProcessing>  
   ...  
</DataItem>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Automatic*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[DataItem](../data-type/dataitem-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Preserve*|Preserves the null value.<br /><br /> Note: This value is not supported for distinct count measures.|  
|*Error*|Raises a null key error. The value of [NullKeyNotAllowed](nullkeynotallowed-element-assl.md) determines how the instance reacts to the error.<br /><br /> Note: This value is not supported for measures.|  
|*UnknownMember*|Generates an unknown member and raises a null conversion error. The value of [NullKeyConvertedToUnknown](nullkeyconvertedtounknown-element-assl.md) determines how the instance reacts to the error.<br /><br /> Note: This value is not supported for columns associated with measures.|  
|*ZeroOrBlank*|Converts the null value to zero (for numeric data items) or a blank string (for string data items).<br /><br /> Note: This value provides compatibility with previous versions of Analysis Services.|  
|*Automatic*|Uses the default processing appropriate for the element:<br /><br /> *ZeroOrBlank* for OLAP data items.<br /><br /> *UnknownMember* for data mining data items.|  
  
 The enumeration that corresponds to the allowed values for **NullProcessing** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.NullProcessing>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

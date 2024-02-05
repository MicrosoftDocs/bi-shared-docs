---
title: "InvalidXmlCharacters Element (ASSL) | Microsoft Docs"
description: Learn about the InvalidXmlCharacters property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# InvalidXmlCharacters Element (ASSL)

  Specifies the handling method for XML characters in the source data that are not valid.  
  
## Syntax  
  
```xml  
  
<DataItem>  
   ...  
   <InvalidXmlCharacters>...</InvalidXmlCharacters>  
   ...  
</DataItem  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Preserve*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[DataItem](../data-type/dataitem-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Preserve*|Invalid XML characters are preserved.|  
|*Remove*|Invalid XML characters are removed.|  
|*Replace*|Invalid XML characters are replaced with question mark (?) characters.|  
  
 The enumeration that corresponds to the allowed values for **InvalidXmlCharacters** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.InvalidXmlCharacters>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

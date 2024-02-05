---
title: "Usage Element (DimensionAttribute) (ASSL) | Microsoft Docs"
description: Learn about the Usage property element for the dimension attribute in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# Usage Element (DimensionAttribute) (ASSL)

  Describes how an attribute is used.  
  
## Syntax  
  
```xml  
  
<DimensionAttribute>  
      ...  
   <Usage>...</Usage>  
   ...  
</DimensionAttribute>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Regular*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Regular*|The attribute is a regular attribute.|  
|*Key*|The attribute is a key attribute.|  
|*Parent*|The attribute is a parent attribute.|  
  
 The enumeration that corresponds to the allowed values for **Usage** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.AttributeUsage>.  

  
  

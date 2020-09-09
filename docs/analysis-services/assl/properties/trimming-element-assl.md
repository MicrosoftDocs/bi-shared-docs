---
title: "Trimming Element (ASSL) | Microsoft Docs"
description: Learn about the Trimming property element in the Analysis Services Scripting Language (ASSL) schema.
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
# Trimming Element (ASSL)

  Specifies how data from the data source is trimmed.  
  
## Syntax  
  
```xml  
  
<DataItem>  
   ...  
   <Trimming>...</Trimming>  
   ...  
</DataItem>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Right*|  
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
|*Left*|Data is trimmed on the left.|  
|*Right*|Data is trimmed on the right.|  
|*LeftRight*|Data is trimmed on the left and right.|  
|*None*|Data is not trimmed.|  
  
 The enumeration that corresponds to the allowed values for **Trimming** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Trimming>.  
  
 The element that corresponds to the parent of **Trimming** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.DataItem>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

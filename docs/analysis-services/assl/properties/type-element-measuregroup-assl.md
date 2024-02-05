---
title: "Type Element (MeasureGroup) (ASSL) | Microsoft Docs"
description: Learn about the Type property element for MeasureGroup in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# Type Element (MeasureGroup) (ASSL)

  Specifies the type of the [MeasureGroup](../objects/measuregroup-element-assl.md).  
  
## Syntax  
  
```xml  
  
<MeasureGroup>  
   ...  
   <Type>...</Type>  
   ...  
</MeasureGroup>  
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
|Parent element|[MeasureGroup](../objects/measuregroup-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Regular*|Contains regular measures.|  
|*ExchangeRate*|Contains foreign exchange rate measures.|  
|*Sales*|Contains sales measures.|  
|*Budget*|Contains budget measures.|  
|*FinancialReporting*|Contains financial reporting measures.|  
|*Marketing*|Contains marketing measures.|  
|*Inventory*|Contains inventory measures.|  
  
 The enumeration that corresponds to the allowed values for **Type** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MeasureGroupType>.  
  
 The element that corresponds to the parent of **Type** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MeasureGroup>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

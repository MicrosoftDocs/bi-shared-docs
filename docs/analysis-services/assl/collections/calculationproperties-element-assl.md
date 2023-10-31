---
title: "CalculationProperties Element (ASSL) | Microsoft Docs"
description: Learn about the CalculationProperties collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# CalculationProperties Element (ASSL)

  Contains the collection of [CalculationProperty](../objects/calculationproperty-element-assl.md) elements associated with an [MdxScript](../objects/mdxscript-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<MdxScript>  
   ...  
   <CalculationProperties>  
      <CalculationProperty>...</CalculationProperty>  
   </CalculationProperties>  
   ...  
</MdxScript>  
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
|Parent elements|[MdxScript](../objects/mdxscript-element-assl.md)|  
|Child elements|[CalculationProperty](../objects/calculationproperty-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.CalculationPropertyCollection>.  

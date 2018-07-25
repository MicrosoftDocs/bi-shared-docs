---
title: "ReportParameter Element (ASSL) | Microsoft Docs"
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
# ReportParameter Element - ASSL

  Contains the name and value of a parameter that is passed to a  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] report at run time.  
  
## Syntax  
  
```xml  
  
<ReportParameters>  
      <ReportParameter>  
      <Name>...</Name>  
      <Value>...</Value>  
   </ReportParameter>  
</ReportParameters>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[ReportParameters](collections/reportparameters-element-assl.md)|  
|Child elements|[Name](properties/name-element-assl.md), [Value](properties/value-element-assl.md)|  
  
## Remarks  
 The **Value** element must contain a Multidimensional Expressions (MDX) expression.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ReportParameter>.  
  
## See Also  
 [ReportAction Data Type &#40;ASSL&#41;](data-type/reportaction-data-type-assl.md)   
 [Action Element &#40;ASSL&#41;](objects/action-element-assl.md)   
 [Objects &#40;ASSL&#41;](objects/objects-assl.md)  
  
  

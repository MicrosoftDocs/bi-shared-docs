---
title: "ReportFormatParameter Element (ASSL) | Microsoft Docs"
description: Learn about the ReportFormatParameter object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference

---
# ReportFormatParameter Element - ASL

  Contains the name and value of a parameter that specifies how a  Reporting Service report is formatted at run time.  
  
## Syntax  
  
```xml  
  
<ReportFormatParameters>  
   <ReportFormatParameter>  
      <Name>...</Name>  
      <Value>...</Value>  
   </ReportFormatParameter>  
</ReportFormatParameters>  
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
|Parent element|[ReportFormatParameters](../collections/reportformatparameters-element-assl.md)|  
|Child elements|[Name](../properties/name-element-assl.md), [Value](../properties/value-element-assl.md)|  
  
## Remarks  
 The element that corresponds to the parent of **ReportFormatParameter** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ReportAction>.  
  
## See Also  
 [ReportAction Data Type &#40;ASSL&#41;](../data-type/reportaction-data-type-assl.md)   
 [Action Element &#40;ASSL&#41;](../objects/action-element-assl.md)   
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

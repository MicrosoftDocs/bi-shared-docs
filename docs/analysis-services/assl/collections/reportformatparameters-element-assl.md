---
title: "ReportFormatParameters Element (ASSL) | Microsoft Docs"
description: Learn about the ReportFormatParameters collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# ReportFormatParameters Element (ASSL)

  Contains the collection of [ReportFormatParameter](../objects/reportformatparameter-element-asl.md) elements for a [ReportAction](../data-type/reportaction-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Action xsi:type="ReportAction">  
   ...  
   <ReportFormatParameters>  
      <ReportFormatParameter>...</ReportFormatParameter>  
   </ReportFormatParameters>  
   ...  
</Action>  
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
|Parent elements|[Action](../objects/action-element-assl.md) of type [ReportAction](../data-type/reportaction-data-type-assl.md)|  
|Child elements|[ReportFormatParameter](../objects/reportformatparameter-element-asl.md)|  
  
## Remarks  
 The element that corresponds to the parent of **ReportFormatParameters** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ReportAction>.  

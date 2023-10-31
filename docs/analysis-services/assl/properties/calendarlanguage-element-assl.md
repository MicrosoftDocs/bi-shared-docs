---
title: "CalendarLanguage Element (ASSL) | Microsoft Docs"
description: Learn about the CalendarLanguage property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# CalendarLanguage Element (ASSL)

  Defines the calendar language used for the [TimeBinding](../data-type/timebinding-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<TimeBinding>  
   ...  
   <CalendarLanguage>...</CalendarLanguage>  
   ...  
</TimeBinding>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Integer|  
|Default value|**1033**|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[TimeBinding](../data-type/timebinding-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 This is the language in which dimension member names are created. The language of captions should be defined using integer-based LCID codes. For example, the default value represents the English-US LCID.  
  
 The element that corresponds to the parent of **CalendarLanguage** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.TimeBinding>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

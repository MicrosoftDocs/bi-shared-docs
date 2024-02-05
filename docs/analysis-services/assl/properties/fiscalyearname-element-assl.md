---
title: "FiscalYearName Element (ASSL) | Microsoft Docs"
description: Learn about the FiscalYearName property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# FiscalYearName Element (ASSL)

  Defines the naming convention for the name of the fiscal year for a [TimeBinding](../data-type/timebinding-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<TimeBinding>  
   ...  
   <FiscalYearName>...</FiscalYearName>  
   ...  
</TimeBinding>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*NextCalendarYearName*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[TimeBinding](../data-type/timebinding-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*CalendarYearName*|Assigns the fiscal year the name of the current calendar year.|  
|*NextCalendarYearName*|Assigns the fiscal year the name of the next calendar year.|  
  
 The enumeration that corresponds to the allowed values for **FiscalYearName** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.FiscalYearName>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

---
title: "TimeBinding Data Type (ASSL) | Microsoft Docs"
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
# TimeBinding Data Type (ASSL)

  Defines a derived data type that represents a binding to time periods.  
  
## Syntax  
  
```xml  
  
<TimeBinding>  
   <!-- The following elements extend Binding -->  
      <CalendarStartDate>...</CalendarStartDate>  
      <CalendarEndDate>...</CalendarEndDate>  
      <FirstDayOfWeek>...</FirstDayOfWeek>  
   <CalendarLanguage>...</CalendarLanguage>  
   <FiscalFirstMonth>...</FiscalFirstMonth>  
   <FiscalFirstDayOfMonth>...</FiscalFirstDayOfMonth>  
   <FiscalYearName>...</FiscalYearName>  
   <ReportingFirstMonth>...</ReportingFirstMonth>  
   <ReportingFirstWeekOfMonth>...</ReportingFirstWeekOfMonth>  
   <ReportingWeekToMonthPattern>...</ReportingWeekToMonthPattern>  
   <ManufacturingFirstMonth>...</ManufacturingFirstMonth>  
   <ManufacturingFirstWeekOfMonth>...</ManufacturingFirstWeekOfMonth>  
   <ManufacturingExtraMonthQuarter>...</ManufacturingExtraMonthQuarter>  
</TimeBinding>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[Binding](data-type/binding-data-type-assl.md)|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[CalendarEndDate](properties/calendarenddate-element-assl.md), [CalendarLanguage](properties/calendarlanguage-element-assl.md), [CalendarStartDate](properties/calendarstartdate-element-assl.md), [FirstDayOfWeek](properties/firstdayofweek-element-assl.md), [FiscalFirstDayOfMonth](properties/fiscalfirstdayofmonth-element-assl.md), [FiscalFirstMonth](properties/fiscalfirstmonth-element-assl.md), [FiscalYearName](properties/fiscalyearname-element-assl.md), [ManufacturingExtraMonthQuarter](properties/manufacturingextramonthquarter-element-assl.md), [ManufacturingFirstMonth](properties/manufacturingfirstmonth-element-assl.md), [ManufacturingFirstWeekOfMonth](properties/manufacturingfirstweekofmonth-element-assl.md), [ReportingFirstMonth](properties/reportingfirstmonth-element-assl.md), [ReportingFirstWeekOfMonth](properties/reportingfirstweekofmonth-element-assl.md), [ReportingWeekToMonthPattern](properties/reportingweektomonthpattern-element-assl.md)|  
|Derived elements|See [Binding](data-type/binding-data-type-assl.md)|  
  
## Remarks  
 For more information about the **Binding** type, including tables of Analysis Services Scripting Language (ASSL) objects of the **Binding** type and the inheritance hierarchy of **Binding** types, see [Binding Data Type &#40;ASSL&#41;](data-type/binding-data-type-assl.md).  
  
 For an overview of data bindings in ASSL, see [Data Sources and Bindings &#40;SSAS Multidimensional&#41;](../../../analysis-services/multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.TimeBinding>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](data-type/analysis-services-scripting-language-xml-data-types-assl.md)  
  
  

---
title: "RefreshPolicy Element (ASSL) | Microsoft Docs"
description: Learn about the RefreshPolicy property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# RefreshPolicy Element (ASSL)

  Determines how often the dynamic part of the dimension or measure group (as specified by the [Persistence](persistence-element-assl.md) element) is checked for changes.  
  
## Syntax  
  
```xml  
  
<DimensionBinding> <!-- or MeasureGroupBinding -->  
   ...  
   <RefreshPolicy>...</RefreshPolicy>  
   ...  
</DimensionBinding>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|See the table below.|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
|Ancestor or Parent|Default Value|  
|------------------------|-------------------|  
|[DimensionBinding](../data-type/dimensionbinding-data-type-assl.md)|*ByQuery*|  
|[MeasureGroupBinding](../data-type/measuregroupbinding-data-type-assl.md)|None|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[DimensionBinding](../data-type/dimensionbinding-data-type-assl.md), [MeasureGroupBinding](../data-type/measuregroupbinding-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*ByQuery*|Every query checks to see whether the source data has changed.|  
|*ByInterval*|Source data is only checked for changes at the interval specified by [RefreshInterval](refreshinterval-element-assl.md).|  
  
 The enumeration that corresponds to the allowed values for **RefreshPolicy** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.RefreshPolicy>.  
  
## See Also  
 [Persistence Element &#40;ASSL&#41;](persistence-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

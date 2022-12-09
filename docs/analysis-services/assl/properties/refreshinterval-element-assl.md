---
title: "RefreshInterval Element (ASSL) | Microsoft Docs"
description: Learn about the RefreshInterval property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: owend

ms.topic: reference
author: minewiskan
ms.author: owend

---
# RefreshInterval Element (ASSL)

  Specifies the interval at which the bound data associated with the parent element is refreshed.  
  
## Syntax  
  
```xml  
  
<DimensionBinding> <!-- or MeasureGroupBinding, ProactiveCachingIncrementalProcessingBinding, ProactiveCachingQueryBinding -->  
   ...  
   <RefreshInterval>...</RefreshInterval>  
   ...  
</DimensionBinding>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|XML duration|  
|Default value|When the Ancestor or Parent is [ProactiveCachingIncrementalProcessingBinding](../data-type/proactivecachingincrementalprocessingbinding-data-type-assl.md) or [ProactiveCachingQueryBinding](../data-type/proactivecachingquerybinding-data-type-assl.md), the default value is PT-1s. In all other cases, it is PT1m.|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[DimensionBinding](../data-type/dimensionbinding-data-type-assl.md), [MeasureGroupBinding](../data-type/measuregroupbinding-data-type-assl.md), [ProactiveCachingIncrementalProcessingBinding](../data-type/proactivecachingincrementalprocessingbinding-data-type-assl.md), [ProactiveCachingQueryBinding](../data-type/proactivecachingquerybinding-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The elements that correspond to the parents of **RefreshInterval** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.DimensionBinding>, <xref:Microsoft.AnalysisServices.MeasureGroupBinding>, <xref:Microsoft.AnalysisServices.ProactiveCachingIncrementalProcessingBinding>, and <xref:Microsoft.AnalysisServices.ProactiveCachingQueryBinding>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

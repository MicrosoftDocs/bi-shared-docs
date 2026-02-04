---
title: "OptimizedState Element (ASSL) | Microsoft Docs"
description: Learn about the OptimizedState property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: eur

ms.topic: reference
author: eric-urban
ms.author: eur

---
# OptimizedState Element (ASSL)

  Determines the level of optimization that is applied to the hierarchy.  
  
## Syntax  
  
```xml  
  
<CubeHierarchy>  
   ...  
   <OptimizedState>...</OptimizedState>  
   ...  
</CubeHierarchy>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*FullyOptimized*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[CubeHierarchy](../data-type/cubehierarchy-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*FullyOptimized*|The instance builds indexes for the hierarchy to improve query performance.|  
|*NotOptimized*|The instance does not build additional indexes.|  
  
 The enumeration that corresponds to the allowed values for **OptimizedState** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.OptimizationType>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

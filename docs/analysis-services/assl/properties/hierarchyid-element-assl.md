---
title: "HierarchyID Element (ASSL) | Microsoft Docs"
ms.date: 7/25/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
---
# HierarchyID Element (ASSL)

  Contains the identifier (ID) for a [CubeHierarchy](../data-type/cubehierarchy-data-type-assl.md), [MeasureGroupHierarchy](../data-type/measuregrouphierarchy-data-type-assl.md), or [PerspectiveHierarchy](../data-type/perspectivehierarchy-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<CubeHierarchy> <!-- or MeasureGroupHierarchy, PerspectiveHierarchy -->  
      ...  
   <HierarchyID>...</HierarchyID>  
      ...  
</CubeHierarchy>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[CubeHierarchy](../data-type/cubehierarchy-data-type-assl.md), [MeasureGroupHierarchy](../data-type/measuregrouphierarchy-data-type-assl.md), [PerspectiveHierarchy](../data-type/perspectivehierarchy-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The elements that correspond to the parents of **HierarchyID** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.CubeHierarchy> and <xref:Microsoft.AnalysisServices.PerspectiveHierarchy>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

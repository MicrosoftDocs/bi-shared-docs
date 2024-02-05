---
title: "AttributeHierarchyOptimizedState Element (ASSL) | Microsoft Docs"
description: Learn about the AttributeHierarchyOptimizedState property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# AttributeHierarchyOptimizedState Element (ASSL)

  Determines the level of optimization applied to the attribute hierarchy.  
  
## Syntax  
  
```xml  
  
<DimensionAttribute> <!-- or CubeAttribute -->  
   ...  
   <AttributeHierarchyOptimizedState>...  
   </AttributeHierarchyOptimizedState>  
   ...  
</DimensionAttribute>  
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
|Parent element|[CubeAttribute](../data-type/cubeattribute-data-type-assl.md), [DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*FullyOptimized*|The instance builds indexes for the attribute hierarchy to improve query performance.|  
|*NotOptimized*|No additional indexes are built by the instance.|  
  
 The enumeration corresponding to the allowed values for **AttributeHierarchyOptimizedState** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.OptimizationType>. The elements that correspond to the parents of **AttributeHierarchyOptimizedState** in the AMO object model are <xref:Microsoft.AnalysisServices.CubeAttribute> and <xref:Microsoft.AnalysisServices.DimensionAttribute>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

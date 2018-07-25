---
title: "HierarchyUniqueNameStyle Element (ASSL) | Microsoft Docs"
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
# HierarchyUniqueNameStyle Element (ASSL)

  Determines how unique names are generated for hierarchies that are contained within the [CubeDimension](data-type/cubedimension-data-type-assl.md).  
  
## Syntax  
  
```xml  
  
<CubeDimension>  
   ...  
   <HierarchyUniqueNameStyle>...</HierarchyUniqueNameStyle>  
   ...  
</CubeDimension>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*IncludeDimensionName*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[CubeDimension](data-type/cubedimension-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*IncludeDimensionName*|The name of the dimension is included as part of the name of the hierarchy.|  
|*ExcludeDimensionName*|The name of the dimension is not included as part of the name of the hierarchy.|  
  
 The element that corresponds to the parent of **HierarchyUniqueNameStyle** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.CubeDimension>.  
  
## See Also  
 [Cube Element &#40;ASSL&#41;](objects/cube-element-assl.md)   
 [Dimension Element &#40;ASSL&#41;](objects/dimension-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties/properties-assl.md)  
  
  

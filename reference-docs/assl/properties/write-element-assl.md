---
title: "Write Element (ASSL) | Microsoft Docs"
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
# Write Element (ASSL)

  Determines whether data or metadata can be written for a given [CubeDimensionPermission](../data-type/cubedimensionpermission-data-type-assl.md) or [Permission](../data-type/permission-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<CubeDimensionPermission> <!-- or Permission -->  
   ...  
   <Write>...</Write>  
   ...  
</CubeDimensionPermission>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*None*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[CubeDimensionPermission](../objects/cubepermission-element-assl.md), [Permission](../data-type/permission-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*None*|No access is permitted to data or metadata from the parent object.|  
|*Allowed*|Write access is permitted to data and metadata from the parent object.|  
  
## Remarks  
 The elements that correspond to the parents of **Write** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.CubeDimensionPermission> and <xref:Microsoft.AnalysisServices.Permission>.  
  
## See Also  
 [Cube Element &#40;ASSL&#41;](../objects/cube-element-assl.md)   
 [Dimension Element &#40;ASSL&#41;](../objects/dimension-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

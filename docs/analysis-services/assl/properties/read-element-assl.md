---
title: "Read Element (ASSL) | Microsoft Docs"
description: Learn about the Read property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 09/14/2020
ms.service: analysis-services
ms.custom: assl
ms.reviewer: owend

ms.topic: reference
author: minewiskan
ms.author: owend

---
# Read Element (ASSL)

  Determines whether data or metadata can be read for a given [CubeDimensionPermission](../data-type/cubedimensionpermission-data-type-assl.md) or [Permission](../data-type/permission-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<CubeDimensionPermission> <!-- or Permission -->  
   ...  
   <Read>...</Read>  
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
|*Allowed*|Read access is permitted to data and metadata from the parent object.|  
  
 The elements that correspond to the parents of **Read** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.CubeDimensionPermission> and <xref:Microsoft.AnalysisServices.Permission>.  
  
## See Also

 [Cube Element &#40;ASSL&#41;](../objects/cube-element-assl.md)   
 [Dimension Element &#40;ASSL&#41;](../objects/dimension-element-assl.md)   
 [CubePermission Element &#40;ASSL&#41;](../objects/cubepermission-element-assl.md)   
 [Permission Data Type &#40;ASSL&#41;](../data-type/permission-data-type-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

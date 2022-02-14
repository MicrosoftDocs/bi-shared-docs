---
title: "MemberUniqueNameStyle Element (ASSL) | Microsoft Docs"
description: Learn about the MemberUniqueNameStyle property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 09/14/2020
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend

---
# MemberUniqueNameStyle Element (ASSL)

  Determines how unique names are generated for members of hierarchies contained within the [CubeDimension](../data-type/cubedimension-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<CubeDimension>  
   ...  
   <MemberUniqueNameStyle>...</MemberUniqueNameStyle>  
   ...  
</CubeDimension>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Native*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[CubeDimension](../data-type/cubedimension-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks

 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Native*|The instance automatically determines the unique names of members.|  
|*NamePath*|The instance generates a compound name consisting of each level and the caption of the member.|  

 The element that corresponds to the parent of **MemberUniqueNameStyle** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.CubeDimension>.  
  
## See Also

 [Cube Element &#40;ASSL&#41;](../objects/cube-element-assl.md)   
 [Dimension Element &#40;ASSL&#41;](../objects/dimension-element-assl.md)   
 [CubeDimension Data Type &#40;ASSL&#41;](../data-type/cubedimension-data-type-assl.md)  
  
  

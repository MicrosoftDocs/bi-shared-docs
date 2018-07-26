---
title: "DefaultMember Element (ASSL) | Microsoft Docs"
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
# DefaultMember Element (ASSL)

  Contains a Multidimensional Expressions (MDX) expression that identifies the default member of the parent element.  
  
## Syntax  
  
```xml  
  
<AttributePermission> <!-- or DimensionAttribute, ManyToManyMeasureGroupDimension, PerspectiveAttribute -->  
      ...  
   <DefaultMember>...</DefaultMember>  
      ...  
</AttributePermission>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[AttributePermission](../objects/attributepermission-element-assl.md), [DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md), [ManyToManyMeasureGroupDimension](../data-type/manytomanymeasuregroupdimension-data-type-assl.md), [PerspectiveAttribute](../data-type/perspectiveattribute-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The **DefaultMember** element defines the default member for the parent element. If **DefaultMember** is not specified or is set to an empty string, Analysis Services chooses a member to use as the default member.  
  
 For **ManyToManyMeasureGroupDimension** elements, the **DefaultMember** element contains an MDX expression that specifies a member in the dimension identified in the **CubeDimensionID** element of the **ManyToManyMeasureGroupDimension**. The MDX expression is similar to the StrToMember MDX function with the CONSTRAINED keyword, in that it cannot include MDX or user-defined functions.  
  
 The elements that correspond to the parents of **DefaultMember** in the Analysis Management Objects (AMO) object model are `<xref:Microsoft.AnalysisServices.AttributePermission>`, `<xref:Microsoft.AnalysisServices.DimensionAttribute>`, and `<xref:Microsoft.AnalysisServices.PerspectiveAttribute>`. 
  
  

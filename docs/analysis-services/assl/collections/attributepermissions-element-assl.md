---
title: "AttributePermissions Element (ASSL) | Microsoft Docs"
description: Learn about the AttributePermissions collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 07/25/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# AttributePermissions Element (ASSL)

  Contains the collection of attribute permissions for an individual [Role](../objects/role-element-assl.md) element on a specific dimension of a [Cube](../objects/cube-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<CubeDimensionPermission> <!-- or DimensionPermission -->  
   <AttributePermissions>  
      <AttributePermission>...</AttributePermission>  
      </AttributePermissions>  
</CubeDimensionPermission>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[CubeDimensionPermission](../data-type/cubedimensionpermission-data-type-assl.md), [DimensionPermission](../objects/dimensionpermission-element-assl.md)|  
|Child elements|[AttributePermission](../objects/attributepermission-element-assl.md)|  
  
## Remarks  
 For **DimensionPermission**, this collection can contain only one **AttributePermission** per attribute.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.AttributePermissionCollection>.  

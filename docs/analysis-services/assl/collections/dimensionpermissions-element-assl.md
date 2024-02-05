---
title: "DimensionPermissions Element (ASSL) | Microsoft Docs"
description: Learn about the DimensionPermissions collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# DimensionPermissions Element (ASSL)

  Contains the collection of permissions applicable to a [Dimension](../objects/dimension-element-assl.md) element or a [CubePermission](../objects/cubepermission-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Dimension> <!-- or CubePermission -->  
   ...  
   <DimensionPermissions>  
            <DimensionPermission>...</DimensionPermission> <!-- parent: Dimension -->  
      <!-- or -->  
      <DimensionPermission xsi:type="CubeDimensionPermission">...</DimensionPermission> <!-- parent: CubePermission -->  
      </DimensionPermissions>  
   ...  
</Dimension>  
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
|Parent elements|[CubePermission](../objects/cubepermission-element-assl.md), [Dimension](../objects/dimension-element-assl.md)|  
|Child elements|[DimensionPermission](../objects/dimensionpermission-element-assl.md)|  
  
## Remarks  
 For **CubePermission** elements, **DimensionPermission** elements in this collection override permissions specified in the **DimensionPermissions** collection of each dimension explicitly referenced. If a dimension is not referenced in this collection, then the **CubePermission** element inherits the permissions specified in the **DimensionPermissions** collection of the dimension.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.DimensionPermissionCollection>.  

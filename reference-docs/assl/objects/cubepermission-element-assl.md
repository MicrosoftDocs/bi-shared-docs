---
title: "CubePermission Element (ASSL) | Microsoft Docs"
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# CubePermission Element (ASSL)

  Defines the permissions of the members of a particular [Role](objects/role-element-assl.md) element in a specific [Cube](objects/cube-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<CubePermissions>  
   <CubePermission>  
      <!-- The following elements extend Permission -->  
      <ReadSourceData>...</ReadSourceData>  
            <DimensionPermissions>...</DimensionPermissions>  
            <CellPermissions>...</CellPermissions>  
   </CubePermission>  
</CubePermissions>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[Permission](data-type/permission-data-type-assl.md)|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur once or more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[CubePermissions](collections/cubepermissions-element-assl.md)|  
|Child elements|[CellPermissions](collections/cellpermissions-element-assl.md), [DimensionPermissions](collections/dimensionpermissions-element-assl.md), [ReadSourceData](properties/readsourcedata-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.CubePermission>.  
  
## See Also  
 [Cube Element &#40;ASSL&#41;](objects/cube-element-assl.md)   
 [Objects &#40;ASSL&#41;](objects/objects-assl.md)  
  
  

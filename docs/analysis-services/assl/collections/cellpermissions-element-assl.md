---
title: "CellPermissions Element (ASSL) | Microsoft Docs"
description: Learn about the CellPermissions collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# CellPermissions Element (ASSL)

  Contains the collection of permissions for cells in the associated [Cube](../objects/cube-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<CubePermission>  
   ...  
   <CellPermissions>  
      <CellPermission>...</CellPermission>  
   </CellPermissions>  
   ...  
</CubePermission>  
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
|Parent elements|[CubePermission](../objects/cubepermission-element-assl.md)|  
|Child elements|[CellPermission](../objects/cellpermission-element-assl.md)|  
  
## Remarks  
 The collection can contain up to one **CellPermission** object for each allowed value of the [Access](../properties/access-element-assl.md) element.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.CellPermissionCollection>.  

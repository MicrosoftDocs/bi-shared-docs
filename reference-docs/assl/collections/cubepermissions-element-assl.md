---
title: "CubePermissions Element (ASSL) | Microsoft Docs"
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
# CubePermissions Element (ASSL)

  Contains the collection of permissions applicable to a [Cube](objects/cube-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Cube>  
   ...  
   <CubePermissions>  
      <CubePermission>...</CubePermission>  
   </CubePermissions>  
   ...  
</Cube>  
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
|Parent elements|[Cube](objects/cube-element-assl.md)|  
|Child elements|[CubePermission](objects/cubepermission-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.CubePermissionCollection>.  

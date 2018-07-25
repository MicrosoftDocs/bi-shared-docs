---
title: "CellPermission Element (ASSL) | Microsoft Docs"
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
# CellPermission Element (ASSL)

  Describes the permissions that members of a [Role](objects/role-element-assl.md) element have on individual cells within a [Cube](objects/cube-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<CellPermissions>  
   <CellPermission>  
      <Access>...</Access>  
            <Description>...</Description>  
      <Expression>...</Expression>  
      <Annotations>...</Annotations>  
   </CellPermission>  
</CellPermissions>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[CellPermissions](collections/cellpermissions-element-assl.md)|  
|Child elements|[Access](properties/access-element-assl.md), [Annotations](collections/annotations-element-assl.md), [Description](properties/description-element-assl.md), [Expression](properties/expression-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.CellPermission>.  
  
## See Also  
 [Objects &#40;ASSL&#41;](objects/objects-assl.md)  
  
  

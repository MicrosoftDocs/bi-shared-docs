---
title: "DimensionPermission Element (ASSL) | Microsoft Docs"
description: Learn about the DimensionPermission object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference

---
# DimensionPermission Element (ASSL)

  Defines the permissions that belong to a particular [Role](../objects/role-element-assl.md) element for a specific database dimension or cube dimension.  
  
## Syntax  
  
```xml  
  
<DimensionPermissions>  
   <DimensionPermission xsi:type="DimensionPermission">...</DimensionPermission> <!-- ancestor: Dimension -->  
   <!-- or -->  
   <DimensionPermission xsi:type="CubeDimensionPermission">...</DimensionPermission> <!-- ancestor: CubePermission -->  
</DimensionPermissions>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|The following are valid Parent (or Ancestor): Data Type pairs:<br /><br /> [Dimension](../objects/dimension-element-assl.md):[DimensionPermission](../data-type/dimensionpermission-data-type-assl.md)<br /><br /> [CubePermission](../objects/cubepermission-element-assl.md):<br />                        [CubeDimensionPermission](../data-type/cubedimensionpermission-data-type-assl.md)|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur once or more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[DimensionPermissions](../collections/dimensionpermissions-element-assl.md)|  
  
## Remarks  
 The corresponding elements in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.DimensionPermission> and <xref:Microsoft.AnalysisServices.CubeDimensionPermission>.  
  
## See Also  
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

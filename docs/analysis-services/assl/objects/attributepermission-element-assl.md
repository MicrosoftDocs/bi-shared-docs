---
title: "AttributePermission Element (ASSL) | Microsoft Docs"
description: Learn about the AttributePermission object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# AttributePermission Element (ASSL)

  Defines the permissions that members of a [Role](../objects/role-element-assl.md) element have on the attributes of an individual dimension in a [Cube](../objects/cube-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<AttributePermissions>  
   <AttributePermission>  
      <AttributeID>...</AttributeID>  
      <Description>...</Description>  
      <DefaultMember>...</DefaultMember>  
            <VisualTotals>...</VisualTotals>  
      <AllowedSet>...</AllowedSet>  
            <DeniedSet>...</DeniedSet>  
      <Annotations>...</Annotations>  
   </AttributePermission>  
</AttributePermissions>  
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
|Parent elements|[AttributePermissions](../collections/attributepermissions-element-assl.md)|  
|Child elements|[AllowedSet](../properties/allowedset-element-assl.md), [Annotations](../collections/annotations-element-assl.md), [AttributeID](../properties/attributeid-element-assl.md), [DefaultMember](../properties/defaultmember-element-assl.md), [DeniedSet](../properties/deniedset-element-assl.md), [Description](../properties/description-element-assl.md), [VisualTotals](../properties/visualtotals-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.AttributePermission>.  
  
## See Also  
 [CubeDimensionPermission Data Type &#40;ASSL&#41;](../data-type/cubedimensionpermission-data-type-assl.md)   
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

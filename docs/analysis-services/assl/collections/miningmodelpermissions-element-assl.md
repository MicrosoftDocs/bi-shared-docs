---
title: "MiningModelPermissions Element (ASSL) | Microsoft Docs"
description: Learn about the MiningModelPermissions collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference

---
# MiningModelPermissions Element (ASSL)

  Contains the collection of permissions for a [MiningModel](../objects/miningmodel-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<MiningModel>  
   ...  
   <MiningModelPermissions>  
      <MiningModelPermission xsi:type="Permission">...</MiningModelPermission>  
   </MiningModelPermissions>  
   ...  
</MiningModel>  
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
|Parent elements|[MiningModel](../objects/miningmodel-element-assl.md)|  
|Child elements|[MiningModelPermission](../objects/miningmodelpermission-element-assl.md) of type [Permission](../data-type/permission-data-type-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MiningModelPermissionCollection>.  

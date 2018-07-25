---
title: "DatabasePermission Element (ASSL) | Microsoft Docs"
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
# DatabasePermission Element (ASSL)

  Defines the default permissions in a [Database](../objects/database-element-assl.md) element for a specific [Role](../objects/role-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<DatabasePermissions>  
      <DatabasePermission xsi:type="Permission">  
      <!-- The following elements extend Permission -->  
      <Administer>...</Administer>  
...</DatabasePermission>  
</DatabasePermissions>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[Permission](../data-type/permission-data-type-assl.md)|  
|Default value|False|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[DatabasePermissions](../collections/databasepermissions-element-assl.md)|  
|Child elements|[Administer](../properties/administer-element-assl.md)|  
  
## Remarks  
 **DatabasePermission** objects can exist only for roles owned by the database, and only one **DatabasePermission** object can exist for any role.  
  
 This element has the following validations under DeploymentMode value 2 (Tabular Models).  
  
-   *Administer* attribute default value is set to **False**, except when the user has administrative privileges. For users with administrative privileges the attribute value is set to **True**.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.DatabasePermission>.  
  
## See Also  
 [Role Element &#40;ASSL&#41;](../objects/role-element-assl.md)   
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

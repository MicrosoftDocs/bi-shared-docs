---
title: "MiningStructurePermission Element (ASSL) | Microsoft Docs"
description: Learn about the MiningStructurePermission object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# MiningStructurePermission Element (ASSL)

  Defines the permissions that members of a [Role](../objects/role-element-assl.md) element have on an individual [MiningStructure](../objects/miningstructure-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<MiningStructurePermissions>  
   <MiningStructurePermission xsi:type="Permission">  
      <AllowDrillthrough>...</AllowDrillthrough>  
  
      <!-- This element also inherits all the child elements listed in Permission -->  
   </MiningStructurePermission>  
</MiningStructurePermissions>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[Permission](../data-type/permission-data-type-assl.md)|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[MiningStructurePermissions](../collections/miningstructurepermissions-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MiningStructurePermission>.  
  
 In SQL Server, the permission **AllowDrillthrough** has been extended to apply to a mining structure. When you assign this permission to a role, any user who is a member of that role can directly query the mining structure by using the following syntax:  
  
```sql  
SELECT <structure column list> FROM <structure>.CASES  
```  
  
 Moreover, if **AllowDrillthrough** is enabled on both the mining structure and the mining model, users can query structure columns that were not included in the mining model by using the following syntax:  
  
```sql  
SELECT StructureColumn('<structure column name>' FROM <model>.CASES  
```  
  
 For example, you create a model using only columns for customer key, customer income, and customer purchases. By using drillthrough, a user can return other structure columns that were not included in the mining model, such as customer contact information.  
  
 Therefore, to protect sensitive data or personal information, you should construct your data source view to mask personal information and grant **AllowDrillthrough** permission on a structure only when necessary.  
 
  

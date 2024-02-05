---
title: "Permission Data Type (ASSL) | Microsoft Docs"
description: Learn about the Permission data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Permission Data Type (ASSL)

  Defines an abstract primitive data type that represents information about an individual permission.  
  
## Syntax  
  
```xml  
  
<Permission>  
   <Name>...</Name>  
   <ID>...</ID>  
   <CreatedTimestamp>...</CreateTimestamp>  
   <LastSchemaUpdate>...</LastSchemaUpdate>  
   <RoleID>...</RoleID>  
   <Description>...</Description>  
   <Process>...</Process>  
   <ReadDefinition>...</ReadDefinition>  
   <Read>...</Read>  
   <Write>...</Write>  
   <Annotations>...</Annotations>  
</Permission>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|None|  
|Derived data types|[CubePermission](../objects/cubepermission-element-assl.md), [DatabasePermission](../objects/databasepermission-element-assl.md), [DimensionPermission](dimensionpermission-data-type-assl.md), [MiningModelPermission](../objects/miningmodelpermission-element-assl.md), [MiningStructurePermission](../objects/miningstructurepermission-element-assl.md)|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[Annotations](../collections/annotations-element-assl.md), [CreatedTimestamp](../properties/createdtimestamp-element-assl.md), [Description](../properties/description-element-assl.md), [ID](../properties/id-element-assl.md), [LastSchemaUpdate](../properties/lastschemaupdate-element-assl.md), [Name](../properties/name-element-assl.md), [Process](../properties/process-element-assl.md), [Read](../properties/read-element-assl.md), [ReadDefinition](../properties/readdefinition-element-assl.md), [RoleID](../properties/roleid-element-assl.md), [Write](../properties/write-element-assl.md)|  
|Derived elements|None|  
  
## Remarks  
 **Permission** serves as the abstract base type for a number of derived permission types used in an instance of Analysis Services.  
  
 This data type has the following validations under DeploymentMode value 2 (tabular server mode).  
  
-   *Process* attribute default value is set to **False**, except when the user has the **Refresh** permission. For users with the **Refresh** permission the *Process* attribute value is set to **True**.  
  
-   *ReadDefinition* attribute value is set to **None**; any other value generates an error.  
  
-   *Read* attribute value is set to **Allowed** for users with the **User** permission and to **None** when the users are assigned to the **Refresh** permission; if a user has both **User** and **Refresh** permissions, then the attribute is set to **Allowed**. For users with administrative privileges the attribute value is set to **Allowed**.  
  
-   *Write* attribute value is set to **None**; any other value generates an error.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Permission>.  
  
## See Also  
 [Role Element &#40;ASSL&#41;](../objects/role-element-assl.md)   
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  

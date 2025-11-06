---
title: "DataSourcePermission Element (ASSL) | Microsoft Docs"
description: Learn about the DataSourcePermission object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference

---
# DataSourcePermission Element (ASSL)

  Defines the default permissions in a [DataSource](../data-type/datasource-data-type-assl.md) data type for a specific [Role](../objects/role-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<DataSourcePermissions>  
   <DataSourcePermission xsi:type="Permission">  
      <!-- No child elements other than those from Permission are defined -->  
...</DataSourcePermission>  
</DataSourcePermissions>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[Permission](../data-type/permission-data-type-assl.md)|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur once or more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[DataSourcePermissions](../collections/datasourcepermissions-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 **DataSourcePermission** objects can exist only for roles owned by the database, and only one **DataSourcePermission** object can exist for any role.  
  
## See Also  
 [Role Element &#40;ASSL&#41;](../objects/role-element-assl.md)   
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

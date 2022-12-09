---
title: "DataSourcePermissions Element (ASSL) | Microsoft Docs"
description: Learn about the DataSourcePermissions collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# DataSourcePermissions Element (ASSL)

  Contains the collection of [DataSourcePermission](../objects/datasourcepermission-element-assl.md) elements associated with a [DataSource](../data-type/datasource-data-type-assl.md) data type.  
  
## Syntax  
  
```xml  
  
<DataSource>  
   ...  
   <DataSourcePermissions>  
      <DataSourcePermission>...</DataSourcePermission>  
   </DataSourcePermissions>  
   ...  
</DataSource>  
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
|Parent elements|[DataSource](../data-type/datasource-data-type-assl.md)|  
|Child elements|[DataSourcePermission](../objects/datasourcepermission-element-assl.md)|  
  
## Remarks  

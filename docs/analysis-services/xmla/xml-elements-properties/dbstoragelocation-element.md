---
title: "DbStorageLocation Element | Microsoft Docs"
description: Learn how the DbStorageLocation element specifies the folder where Analysis Services creates and manages all the database data and metadata files.
ms.date: 01/05/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# DbStorageLocation Element

  Specifies the folder where Analysis Services creates and manages all the database data and metadata files.  
  
## Syntax  
  
```xml  
  
<Database>  
...  
   <ddl100_100:DbStorageLocation>...</ddl100_100:DbStorageLocation>  
...  
</Database>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|""|  
|Cardinality|0-1: Optional element that can occur one time only.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Database](../xml-elements-properties/database-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **DbStorageLocation** database property must be set to an existing UNC folder path or an empty string. An empty string is the default server data folder. If the folder doesn't exist, an error will be raised when executing a **Create**, **Attach**, or **Alter** command.  
  
 In addition, the **DbStorageLocation** database property cannot be set to point to the server data folder or any of its subfolders. If the location points to the server data folder or any of its subfolders, an error will be raised when executing a **Create**, **Attach**, or **Alter** command.  
 
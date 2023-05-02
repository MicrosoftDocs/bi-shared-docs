---
title: "Upgrade encryption schema (SQL Server 2022 Analysis Services) | Microsoft Docs"
description: Learn about upgrading SQL Server 2022 tabular and multidimensional databases to the latest encryption.  
ms.date: 02/09/2023
ms.service: analysis-services
ms.custom:
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || >= sql-analysis-services-2022"
---
# Upgrade encryption

[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]

SQL Server 2022 Analysis Services CU1 and later includes enhanced encryption for certain write operations to the model database schema. To ensure your model databases use the latest encryption, those databases must be upgraded. If encryption isn't upgraded, certain database schema write operations, such as adding a new data source or altering connection strings are blocked and an error is returned.

> [!CAUTION]
> New or upgraded Analysis Services databases with enhanced encryption cannot be loaded if SQL Server CU1 is uninstalled.

## Tabular mode

For tabular model databases at the 1600 and higher compatibility level, the following error can be returned during certain schema write operations:

"**New Tabular database '%{DatabaseName/}' is not using latest encryption schema. Please run RemoveDiscontinuedFeatured command with EnsureProperEncryption option (or restore DB from backup file with the same option) to upgrade to the latest encryption.**"

To upgrade encryption, either backup the database and then restore with the **EnsureProperEncryption** option enabled, or if the database is already loaded, run the following XMLA command in SQL Server Management Studio:

```xml
<RemoveDiscontinuedFeatures xmlns=http://schemas.microsoft.com/analysisservices/2003/engine xmlns:ddl922=http://schemas.microsoft.com/analysisservices/2022/engine/922>
  <DatabaseID>DatabaseName</DatabaseID>
  <ddl922:EnsureProperEncryption>true</ddl922:EnsureProperEncryption>
</RemoveDiscontinuedFeatures>

```

## Multidimensional mode

For multidimensional model databases at all compatibility levels, the following error can be returned during certain schema write operations:

"**Multi-dimensional database '%{DatabaseName/}' is not using latest encryption schema. Please create a backup file and restore DB from backup file with the option EnsureProperEncryption to upgrade to the latest encryption.**"

To upgrade encryption, backup the database and then restore with the **EnsureProperEncryption** option enabled.



## See also

[Backup and restore Analysis Services Databases](../multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
[Compatibility level for tabular models](../tabular-models/compatibility-level-for-tabular-models-in-analysis-services.md)  

---
title: "Upgrade encryption schema (SQL Server 2022 Analysis Services) | Microsoft Docs"
description: Learn about upgrading SQL Server 2022 tabular and multidimensional databases to the latest encryption.  
ms.date: 02/09/2023
ms.service: analysis-services
ms.custom:
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis
monikerRange: "asallproducts-allversions || >= sql-analysis-services-2022"
---
# Enhanced encryption

[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]

SQL Server 2022 Analysis Services (SSAS) CU1 and later versions include enhanced encryption for certain write operations to the model database schema. When upgrading from an earlier SSAS version, you must update your model databases to use the latest encryption. If encryption isn't upgraded, certain database schema write operations, such as adding a new data source or altering connection strings are blocked and an error is returned.

> [!CAUTION]
> New or upgraded Analysis Services databases with enhanced encryption cannot be loaded on earlier versions of SQL Server Analysis Services.

## Upgrading Tabular model databases

For tabular model databases at the 1600 and higher compatibility level, the following error can be returned during certain schema write operations:

"**New Tabular database '%{DatabaseName/}' is not using latest encryption schema. Please run RemoveDiscontinuedFeatured command with EnsureProperEncryption option (or restore DB from backup file with the same option) to upgrade to the latest encryption.**"

To upgrade encryption, either back up the database and then restore with the **EnsureProperEncryption** option enabled by running the following XMLA command in SQL Server Management Studio:

```xml
<Batch xmlns="http://schemas.microsoft.com/analysisservices/2003/engine" Transaction="false" xmlns:ddl100_100="http://schemas.microsoft.com/analysisservices/2008/engine/100/100" xmlns:ddl100="http://schemas.microsoft.com/analysisservices/2008/engine/100">
<Restore xmlns="http://schemas.microsoft.com/analysisservices/2003/engine" xmlns:ddl922="http://schemas.microsoft.com/analysisservices/2022/engine/922">
<File>your_backup_file_pathname</File>
<AllowOverwrite>true</AllowOverwrite>
<ddl922:EnsureProperEncryption>true</ddl922:EnsureProperEncryption>
</Restore>
</Batch>
```

Or, if the database is already loaded, run the following XMLA command in SQL Server Management Studio:

```xml
<RemoveDiscontinuedFeatures xmlns='http://schemas.microsoft.com/analysisservices/2003/engine' xmlns:ddl922='http://schemas.microsoft.com/analysisservices/2022/engine/922'>
  <DatabaseID>DatabaseName</DatabaseID>
  <ddl922:EnsureProperEncryption>true</ddl922:EnsureProperEncryption>
</RemoveDiscontinuedFeatures>

```

## Upgrading Multidimensional model databases

For multidimensional model databases at all compatibility levels, the following error can be returned during certain schema write operations:

"**Multi-dimensional database '%{DatabaseName/}' is not using latest encryption schema. Please create a backup file and restore DB from backup file with the option EnsureProperEncryption to upgrade to the latest encryption.**"

To upgrade encryption, back up the database and then restore with the **EnsureProperEncryption** option enabled.

Or, if the database is already loaded, run the following XMLA command in SQL Server Management Studio:

```xml
<RemoveDiscontinuedFeatures xmlns='http://schemas.microsoft.com/analysisservices/2003/engine' xmlns:ddl922='http://schemas.microsoft.com/analysisservices/2022/engine/922'>
  <DatabaseID>DatabaseName</DatabaseID>
  <ddl922:EnsureProperEncryption>true</ddl922:EnsureProperEncryption>
</RemoveDiscontinuedFeatures>

```

## Key Lifetime Management

SQL Server Analysis Services uses a database encryption key to encrypt sensitive data on a per-database basis, such as data source credentials and connection strings. In SSAS 2025 and later versions, you can use the DBSCHEMA_CATALOGS schema rowset to determine the encryption level of your model databases as well as the age of the database key. Check the ENCRYPTION_LEVEL column and verify that the level is Analysis Services 2022 CU. Check the CRYPTOKEY_UPDATED column for the creation date or last regeneration date of the database encryption key.

You can regenerate the database encryption key by using the RemoveDiscontinuedFeatures command. Like upgrading from legacy encryption described earlier, the RemoveDiscontinuedFeatures command decrypts the securable data, generates a new database encryption key, and then re-encrypts the securable data using the new database encryption key.

```xml
<RemoveDiscontinuedFeatures xmlns='http://schemas.microsoft.com/analysisservices/2003/engine' xmlns:ddl922='http://schemas.microsoft.com/analysisservices/2022/engine/922'>
  <DatabaseID>DatabaseName</DatabaseID>
  <ddl922:EnsureProperEncryption>true</ddl922:EnsureProperEncryption>
</RemoveDiscontinuedFeatures>

```

## Service account change procedures

SQL Server Analysis Services encrypts each database encryption key by using a server-wide encryption key. Enhanced encryption in SSAS 2022 CU1 and later versions then uses the data protection API (DPAPI) to securely protect and access the server encryption key by using information from the current service account and the local machine account. The server encryption key can only be decrypted using the same service account on the local machine. Because of the dependency on the current service account, make sure you follow the below procedures for changing the SQL Server Analysis Services service account.

### Changing the service account of a Multidimensional instance

If you must change the service account of a server instance running in Multidimensional mode, it's essential to backup your model databases, uninstall and then re-install the server, and then restore the model databases. This approach ensures that all securables are properly encrypted, including QueryLogConnectionString and ImpersonationAccount credentials. Alternatively, you can also use an [attach/detach approach](../multidimensional-models/attach-and-detach-analysis-services-databases.md?view=sql-analysis-services-2025&preserve-view=true), but this approach requires you to preserve the existing data folder.

1.	Use SSMS to back up each database into .abf file.

2.	Uninstall the SSAS server instance.

3.	Delete any remnants of the uninstalled server instance, such as leftover data folders or configuration files.

4.	Install a new SSAS server instance and assign a new service account.

5.	Restore the databases from the backup .abf files.

Use caution when implementing these steps to avoid data loss or security vulnerabilities. Always perform data backups and seek guidance from your system administrator prior to making substantial changes to service accounts or server configurations.

### Changing the service account of a Tabular instance

Tabular server instances do not require complete server reinstallation because Tabular servers do not use the server-wide QueryLogConnectionString or ImpersonationAccount credentials. Even though the procedure does not rely on database backups, you should always perform data backups and seek guidance from your system administrator prior to making substantial changes to service accounts or server configurations.

1.	Recommended but optional, use SSMS to back up each database into .abf file.

2.	Detach all model databases.

3.	Stop the SSAS service.

4.	Change the SSAS service account.

5.	Start the SSAS service.

6.	Re-attach all model databases.

## Moving model databases to a different server instance

If you must transfer model databases between servers, it's essential to use a backup/restore or detach/attach method. See [Move an Analysis Services Database](../multidimensional-models/move-an-analysis-services-database.md?view=sql-analysis-services-2025&preserve-view=true) for details about using the detach/attach approach using SSMS, AMO, or XMLA.

## Failover Cluster support

SQL Server 2025 Analysis Services with enhanced encryption can be installed into a Windows Server Failover Cluster (WSFC) to achieve high availability. In a WSFC environment, all server instances must use the same Active Directory domain user account as the service account so that the server encryption key can be decrypted on all server instances. Local Windows accounts, Build-In accounts, and Entra ID accounts are not supported.

> [!NOTE]
SQL Server 2022 Analysis Services CU1 with enhanced encryption does not provide Failover Cluster support. To benefit from enhanced encryption in a Failover Cluster environment, you must upgrade to SQL Server 2025 Analysis Services.

## Troubleshooting

**Problem:** If the backup/restore steps above aren't followed, changing SQL Server 2022 Analysis Services service account can cause the service to fail to start.

The following message in the Log\msmdsrv.log file indicates the service is unable to start because the service account has been changed:

"**Server Gen2 cryptokey is not present, but server assembly object System is set to use server gen2 cryptokey. Terminating server. (Source: \\?\C:\Program Files\Microsoft SQL Server\MSAS16.MSSQLSERVER\OLAP\Log\msmdsrv.log, Type: 1, Category: 289, Event ID: 0x4121005C**"

**Solution:** In the msmdsrv.ini file, in **ConfigurationSettings** > **DataDir**, determine the location of the **Data** folder. Then in the **Data** folder, delete the files with the name containing **.asm.xml**, and all folders with an **.asm** extension.

After deleting the files, restart the Analysis Services service. The .asm files are automatically created again.

The following encrypted properties must then be configured by using SQL Server Management Studio (SSMS):

- Log\QueryLog\QueryLogConnectionString.
- Each data source ImpersonationAccount password or authentication password.

## See also

[Back up and restore Analysis Services Databases](../multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
[Compatibility level for tabular models](../tabular-models/compatibility-level-for-tabular-models-in-analysis-services.md)  

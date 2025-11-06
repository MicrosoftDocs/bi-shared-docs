---
title: "Restore Element (XMLA) | Microsoft Docs"
description: Learn how the Restore element restores a Analysis Services database from a backup file.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference

---
# Restore Element (XMLA)

  Restores a Analysis Services database from a backup file.  
  
## Syntax  
  
```xml  
  
<Command>  
   <Restore>  
      <DatabaseName>...</DatabaseName>  
      <DatabaseID>...</DatabaseID>  
      <File>...</File>  
      <Security>...</Security>  
      <AllowOverwrite>...</AllowOverwrite>  
      <Password>...</Password>  
      <Locations>...</Locations>  
      <DbStorageLocation>...</DbStorageLocation>  
   </Restore>  
</Command>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Command](../xml-elements-properties/command-element-xmla.md)|  
|Child elements|[AllowOverwrite](../xml-elements-properties/allowoverwrite-element-xmla.md), [DatabaseName](../xml-elements-properties/databasename-element-xmla.md), [DatabaseID](../xml-elements-properties/databaseid-element-xmla.md), [File](../xml-elements-properties/file-element-xmla.md), [Locations](../xml-elements-properties/locations-element-xmla.md), [Password](../xml-elements-properties/password-element-xmla.md), [Security](../xml-elements-properties/security-element-xmla.md), [DbStorageLocation](../xml-elements-properties/dbstoragelocation-element.md)|  
  
## Remarks  
 The **Restore** command restores an Analysis Services database specified in the **DatabaseName** element from a backup file and optionally restores remote partitions from remote backup files.  
  
 Depending on the storage mode used by objects stored in the backup file, the **Restore** command restores information as listed in the following table.  
  
|Storage mode|Information|  
|------------------|-----------------|  
|Multidimensional OLAP (MOLAP)|Source data, aggregations, and metadata|  
|Hybrid OLAP (HOLAP)|Aggregations and metadata|  
|Relational OLAP (ROLAP)|Metadata|  
  
 During a **Restore** command, an exclusive lock is placed on the Analysis Services database specified in the **DatabaseName** element. The lock is released after the **Restore** command has completed.  
  
> [!IMPORTANT]  
>  For each backup file, the user who runs the restore command must have permission to read from the backup location specified for each file. To restore an Analysis Services database that is not installed on the server, the user must also be a member of the server role for that Analysis Services instance. To overwrite an Analysis Services database, the user must have one of the following roles: a member of the server role for the Analysis Services instance, or a member of a database role with Full Control (Administrator) permissions on the database to be restored.  
  
> [!NOTE]  
>  After restoring an existing database, the user who restored the database might lose access to the restored database. This loss of access can occur if, at the time that the backup was performed, the user was not a member of the server role or was not a member of the database role with Full Control (Administrator) permissions.
---
title: "Backup Element (XMLA) | Microsoft Docs"
description: Learn how the Backup element backs up a Analysis Services database to a backup file.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Backup Element (XMLA)

  Backs up a Analysis Services database to a backup file.  
  
## Syntax  
  
```xml  
  
<Command>  
   <Backup>  
      <Object>...</Object>  
      <File>...</File>  
      <Security>...</Security>  
      <ApplyCompression>...</ApplyCompression>  
      <AllowOverwrite>...</AllowOverwrite>  
      <Password>...</Password>  
      <BackupRemotePartitions>...</BackupRemotePartitions>  
      <Locations>...</Locations>  
   </Backup>  
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
|Child elements|[AllowOverwrite](../xml-elements-properties/allowoverwrite-element-xmla.md), [ApplyCompression](../xml-elements-properties/applycompression-element-xmla.md), [BackupRemotePartitions](../xml-elements-properties/backupremotepartitions-element-xmla.md), [File](../xml-elements-properties/file-element-xmla.md), [Locations](../xml-elements-properties/locations-element-xmla.md), [Object](../xml-elements-properties/object-element-xmla.md), [Password](../xml-elements-properties/password-element-xmla.md), [Security](../xml-elements-properties/security-element-xmla.md)|  
  
## Remarks  
 The **Backup** command backs up the Analysis Services database specified in the [Object](../xml-elements-properties/object-element-xmla.md) element to a backup file, and optionally backs up remote partitions to remote backup files. If the **Object** element refers to an object other than an Analysis Services database, an error occurs.  
  
 Which information the **Backup** command backs up depends on the storage mode used by objects in the database. The following table identifies the information that is backed up based upon the storage mode used.  
  
|Storage mode|Information that is backed up|  
|------------------|-----------------------------------|  
|Multidimensional OLAP (MOLAP)|Source data, aggregations, and metadata|  
|Hybrid OLAP (HOLAP)|Aggregations and metadata|  
|Relational OLAP (ROLAP)|Metadata|  
  
 During a **Backup** command, a shared lock is placed on the Analysis Services database specified in the **Object** element. The shared lock releases after the **Backup** command has completed.  
  
 Multiple **Backup** commands can be run in parallel, if the commands are included in the [Parallel](../xml-elements-properties/parallel-element-xmla.md) collection of a [Batch](../xml-elements-commands/batch-element-xmla.md) command. The **Parallel** collection enables a database to be backed up into multiple backup files at the same time.  

  
> [!IMPORTANT]  
>  For each backup file, the user who runs the backup command must have permission to write to the backup location specified for each file. Also, the user must have one of the following roles: a member of a server role for the Analysis Services instance, or a member of a database role with Full Control (Administrator) permissions on the database to be backed up.  

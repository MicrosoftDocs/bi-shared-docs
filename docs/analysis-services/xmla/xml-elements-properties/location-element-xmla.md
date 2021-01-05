---
title: "Location Element (XMLA) | Microsoft Docs"
description: Learn how the Location element contains information about a remote server for the parent Backup, Restore, or Synchronize command.
ms.date: 01/05/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Location Element (XMLA)

  Contains information about a remote server for the parent [Backup](../xml-elements-commands/backup-element-xmla.md), [Restore](../xml-elements-commands/restore-element-xmla.md), or [Synchronize](../xml-elements-commands/synchronize-element-xmla.md) command.  
  
## Syntax  
  
```xml  
  
<Backup> <!-- or one of the elements listed below in the Element relationships table -->  
   ...  
   <Location>  
```  
  
```xml  
  
<File>...</File> <!-- for Backup and Restore only -->  
<DataSourceID>...</DataSourceID>  
<DataSourceType>...</DataSourceType> <!-- for Restore and Synchronize only -->  
<ConnectionString>...</ConnectionString> <!-- for Restore and Synchronize only -->  
<Folders>...</Folders> <!-- for Restore and Synchronize only -->  
```  
  
```xml  
  
   </Location>  
   ...  
</Backup>  
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
|Parent elements|[Backup](../xml-elements-commands/backup-element-xmla.md), [Restore](../xml-elements-commands/restore-element-xmla.md), [Synchronize](../xml-elements-commands/synchronize-element-xmla.md)|  
|Child elements|See the table below.|  
  
|Ancestor or Parent|Child Element|  
|------------------------|-------------------|  
|[Backup](../xml-elements-commands/backup-element-xmla.md)|[DataSourceID](../xml-elements-properties/datasourceid-element-xmla.md), [File](../xml-elements-properties/file-element-xmla.md)|  
|[Restore](../xml-elements-commands/restore-element-xmla.md)|[ConnectionString](../xml-elements-properties/connectionstring-element-xmla.md), [DataSourceID](../xml-elements-properties/datasourceid-element-xmla.md), [DataSourceType](../xml-elements-properties/datasourcetype-element-xmla.md), [File](../xml-elements-properties/file-element-xmla.md), [Folders](../xml-elements-properties/folders-element-xmla.md)|  
|[Synchronize](../xml-elements-commands/synchronize-element-xmla.md)|[ConnectionString](../xml-elements-properties/connectionstring-element-xmla.md), [DataSourceID](../xml-elements-properties/datasourceid-element-xmla.md), [DataSourceType](../xml-elements-properties/datasourcetype-element-xmla.md), [Folders](../xml-elements-properties/folders-element-xmla.md)|  
  
## Remarks  
 For **Backup** commands, the **Location** element provides information about creating a remote backup file for a remote instance of Analysis Services.  
  
 For **Restore** commands, the **Location** element provides information about identifying and connecting to a remote Analysis Services instance, as well as the remote backup file used to restore remote partitions on that remote instance.  
  
 For **Synchronize** commands, the **Location** element describes either a data source to be used by the target instance or a remote instance defined on the source instance that must be synchronized with the target instance, depending on the value of the **DataSourceType** element for the parent **Synchronize** command.  
 
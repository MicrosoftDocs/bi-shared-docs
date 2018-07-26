---
title: "File Element (XMLA) | Microsoft Docs"
ms.date: 07/24/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# File Element (XMLA)

  Identifies a file to be used by the parent [Backup](../xml-elements-commands/backup-element-xmla.md) or [Restore](../xml-elements-commands/restore-element-xmla.md) command, or by the parent [Location](../xml-elements-properties/location-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<Backup> <!-- or one of the elements listed below in the Element relationships table -->  
   ...  
   <File>...</File>  
   ...  
</Backup>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Backup](../xml-elements-commands/backup-element-xmla.md), [Location](../xml-elements-properties/location-element-xmla.md), [Restore](../xml-elements-commands/restore-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **File** element contains a UNC file name, and the parent element determines the use of the **File** element.  
  
 For **Backup** commands, the **File** element determines the name of the backup file created by the **Backup** command. If a path is not specified as part of the file name, the path specified in the **BackupDir** configuration property for the instance of Analysis Services is used. If the specified file already exists, an error occurs unless the **AllowOverwrite** element of the parent **Backup** command is set to **True**.  
  
 For **Restore** commands, the **File** element determines the name of the backup file to be restored by the **Restore** command.  
  
 For **Location** elements, the **File** element describes a remote backup file for an Analysis Services instance that contains remote partitions. 

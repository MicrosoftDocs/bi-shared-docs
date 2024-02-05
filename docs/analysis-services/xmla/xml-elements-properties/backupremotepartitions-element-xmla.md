---
title: "BackupRemotePartitions Element (XMLA) | Microsoft Docs"
description: Learn how the BackupRemotePartitions element determines whether the parent Backup command backs up remote partitions associated with the object.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# BackupRemotePartitions Element (XMLA)

  Determines whether the parent [Backup](../xml-elements-commands/backup-element-xmla.md) command backs up remote partitions associated with the object.  
  
## Syntax  
  
```xml  
  
<Backup>  
   ...  
   <BackupRemotePartitions>...</BackupRemotePartitions>  
   ...  
</Backup>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Boolean|  
|Default value|False|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Backup](../xml-elements-commands/backup-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 If **BackupRemotePartitions** is set to **True**, a **Locations** element that contains one or more **Location** elements must be included in the **Backup** command, or an error occurs.
  

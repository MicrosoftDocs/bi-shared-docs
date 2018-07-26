---
title: "BackupRemotePartitions Element (XMLA) | Microsoft Docs"
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
  

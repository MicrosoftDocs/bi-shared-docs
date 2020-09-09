---
title: "Password Element (XMLA) | Microsoft Docs"
description: Learn how the Password element determines the password to be used by the parent Backup or Restore command for encrypting or decrypting a backup file.
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
# Password Element (XMLA)

  Determines the password to be used by the parent [Backup](../xml-elements-commands/backup-element-xmla.md) or [Restore](../xml-elements-commands/restore-element-xmla.md) command for encrypting or decrypting a backup file.  
  
## Syntax  
  
```xml  
  
<Backup> <!-- or Restore -->  
   ...  
   <Password>...</Password>  
   ...  
</Backup>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Backup](../xml-elements-commands/backup-element-xmla.md), [Restore](../xml-elements-commands/restore-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 For **Backup** commands, if the **Password** element is not included or contains an empty string, the backup file is not encrypted.  
  
 For **Restore** commands, if the **Password** element is not included or contains an empty string while attempting to restore an encrypted backup file, an error occurs.  
  
 If **Location** elements are included in either a **Backup** or a **Restore** command, the same **Password** element is used for both backup and remote backup files.
  
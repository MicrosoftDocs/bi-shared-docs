---
title: "Security Element (XMLA) | Microsoft Docs"
description: Learn how the Security element specifies how to back up or restore security definitions, such as roles and permissions, during a Backup or Restore command.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Security Element (XMLA)

  Specifies how to back up or restore security definitions, such as roles and permissions, during a Backup or Restore command.  
  
## Syntax  
  
```xml  
  
<Backup> <!-- or Restore -->  
   ...  
   <Security>...</Security>  
   ...  
</Backup>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*SkipMembership*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Backup](../xml-elements-commands/backup-element-xmla.md), [Restore](../xml-elements-commands/restore-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **Security** element determines whether the security definitions, such as roles and permissions, defined on a Analysis Services database are backed up or restored during, respectively, a **Backup** or **Restore** command. This element also determines if the Windows user accounts and groups defined as members of the security definitions are included as part of the **Backup** or **Restore** command.  
  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*SkipMembership*|Include security definitions, but exclude membership information, during **Backup** or **Restore** commands.|  
|*CopyAll*|Include security definitions and membership information during **Backup** or **Restore** commands.|  
|*IgnoreSecurity*|Exclude security definitions during **Backup** or **Restore** commands.|  
 
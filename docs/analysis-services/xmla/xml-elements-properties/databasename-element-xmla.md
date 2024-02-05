---
title: "DatabaseName Element (XMLA) | Microsoft Docs"
description: Learn how the DatabaseName element identifies the Analysis Services database to be restored by the parent Restore command.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# DatabaseName Element (XMLA)

  Identifies the Analysis Services database to be restored by the parent [Restore](../xml-elements-commands/restore-element-xmla.md) command.  
  
## Syntax  
  
```xml  
  
<Restore>  
   ...  
   <DatabaseName>...</DatabaseName>  
   ...  
</Restore>  
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
|Parent elements|[Restore](../xml-elements-commands/restore-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **DatabaseName** element identifies the database into which the **Restore** command restores a backup file. If this element is not specified or contains an empty string, the name of the database contained in the backup file is used.  
  
 If the database already exists on the target instance, an error occurs unless the **AllowOverwrite** element for the parent **Restore** command is set to **True**.  

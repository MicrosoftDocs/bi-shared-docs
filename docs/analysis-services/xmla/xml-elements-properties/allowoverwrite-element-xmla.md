---
title: "AllowOverwrite Element (XMLA) | Microsoft Docs"
description: Learn how the AllowOverwrite element determines whether the parent Backup or Restore command attempts to overwrite the target file or database.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# AllowOverwrite Element (XMLA)

  Determines whether the parent [Backup](../xml-elements-commands/backup-element-xmla.md) or [Restore](../xml-elements-commands/restore-element-xmla.md) command attempts to overwrite the target file or database.  
  
## Syntax  
  
```xml  
  
<Backup> <!-- or Restore -->  
   ...  
   <AllowOverwrite>...</AllowOverwrite>  
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
|Parent elements|[Backup](../xml-elements-commands/backup-element-xmla.md), [Restore](../xml-elements-commands/restore-element-xmla.md)|  
|Child elements|None|  
  
## Remarks

 For **Backup** commands, the **AllowOverwrite** element determines whether the command can overwrite the backup file specified in the **File** element.  
  
 For **Restore** elements, the **AllowOverwrite** element determines whether the command can overwrite the Analysis Services database specified in the **DatabaseName** element.  
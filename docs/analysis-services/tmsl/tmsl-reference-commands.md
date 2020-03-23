---
title: "Commands in Tabular Model Scripting Language (TMSL) | Microsoft Docs"
ms.date: 07/20/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tmsl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# TMSL Reference - Commands

[!INCLUDE[ssas-appliesto-sql2016-later-aas-pbip](../../includes/ssas-appliesto-sql2016-later-aas-pbip.md)]

  You can execute commands on an XMLA endpoint, formulating object definitions in JSON using the Tabular Model Scripting Language (TMSL), against tabular model databases. See [Object Definitions in Tabular Model Scripting Language &#40;TMSL&#41;](tmsl-reference-tabular-objects.md) for a list of objects used with the following commands.  
  
## Object operations  
  
|||  
|-|-|  
|[Alter command &#40;TMSL&#41;](alter-command-tmsl.md)|Make inline modifications to an object without having to specify the full definition.|  
|[Create command &#40;TMSL&#41;](create-command-tmsl.md)|Creates a new object, including its descendants.|  
|[CreateOrReplace command &#40;TMSL&#41;](createorreplace-command-tmsl.md)|Create or replace parts of an object definition. The full definition must be provided.|  
|[Delete command &#40;TMSL&#41;](delete-command-tmsl.md)|Delete an object, including its descendants.|  
  
## Data refresh operations  
  
|||  
|-|-|  
|[MergePartitions command &#40;TMSL&#41;](mergepartitions-command-tmsl.md)|Merge a target partition into a source, and delete the target.|  
|[Refresh command &#40;TMSL&#41;](refresh-command-tmsl.md)|Process a database, table, or partition.|  
  
## Scripting  
  
|||  
|-|-|  
|[Sequence command &#40;TMSL&#41;](sequence-command-tmsl.md)|Batch operations sequentially or in parallel|  
  
## Database management operations  
  
|||  
|-|-|  
|[Attach command &#40;TMSL&#41;](attach-command-tmsl.md)|Adds a file to the server.|  
|[Detach command &#40;TMSL&#41;](detach-command-tmsl.md)|Removes a file from the servers.|  
|[Backup command &#40;TMSL&#41;](backup-command-tmsl.md)|Creates a backup file of a database.|  
|[Restore command &#40;TMSL&#41;](restore-command-tmsl.md)|Restores database to the server.|  
|[Synchronize command &#40;TMSL&#41;](synchronize-command-tmsl.md)|Synchronizes a tabular database with another existing database.| 
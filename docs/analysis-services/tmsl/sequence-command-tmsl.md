---
title: "Sequence command (TMSL) | Microsoft Docs"
description: Use the Sequence command to run a consecutive set of operations in batch mode on an instance of Analysis Services.
ms.date: 07/11/2019
ms.service: analysis-services
ms.custom: tmsl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Sequence command (TMSL)

[!INCLUDE[appliesto-sql2016-later-aas-pbip](../includes/appliesto-sql2016-later-aas-pbip.md)]

  Use the **Sequence** command to run a consecutive set of operations in batch mode on an instance of Analysis Services.  The entire command and all of its component parts must complete in order for the transaction to succeed.  
  
 The following commands can be run sequentially, except for the **Refresh** command which runs in parallel to process multiple objects concurrently.  
  
- [Create command &#40;TMSL&#41;](create-command-tmsl.md)  
  
- [CreateOrReplace command &#40;TMSL&#41;](createorreplace-command-tmsl.md)  
  
- [Alter command &#40;TMSL&#41;](alter-command-tmsl.md)  
  
- [Delete command &#40;TMSL&#41;](delete-command-tmsl.md)  
  
- [Refresh command &#40;TMSL&#41;](refresh-command-tmsl.md)  
  
- [Backup command &#40;TMSL&#41;](backup-command-tmsl.md)  
  
- [Restore command &#40;TMSL&#41;](restore-command-tmsl.md)  
  
- [Attach command &#40;TMSL&#41;](attach-command-tmsl.md)  
  
- [Detach command &#40;TMSL&#41;](detach-command-tmsl.md)  
  
## Request  

 **maxParallelism** is an optional property that determines whether **Refresh** operations run sequentially or in parallel.  
  
 The default behavior is to use as much parallelism as possible. By embedding **Refresh** within **Sequence**, you can control the exact number of threads used during processing, including limiting the operation to just one thread.  
  
> [!NOTE]  
>  The integer assigned to **maxParallelism** determines the maximum number of threads used during processing. Valid values are any positive integer. Setting the value to 1 equals not parallel (uses one thread).  
  
 Only **Refresh** runs in parallel. If you modify **maxParallelism** to use a fixed number of threads, be sure to review the properties on the [Refresh command &#40;TMSL&#41;](refresh-command-tmsl.md) to understand the potential impact. It's possible to set properties in a way that undermines parallelism even when you've made multiple threads available. The following sequence of refresh types will give you the best degree of parallelism:  
  
- First, specify Refresh for all objects using ClearValues  
  
- Next, specify Refresh for all objects using DataOnly  
  
- Last specify Refresh for all objects using Full, Calculate, Automatic or Add  
  
 Any variation on this will break parallelism.  
  
```json   
{   
  "sequence":    
    {   
      "maxParallelism": 3,   
      "operations": [   
        {   
          "mergepartitions": {   
            "sources": [   
              {   
                "database": "salesdatabase",   
                "table": "Sales",   
                "partition": "partition1"   
              },   
              {   
                "database": "salesdatabase",   
                "table": "Sales",   
                "partition": "partition2"   
              }   
            ]   
          }   
        },   
        {   
          "refresh": {   
            "type": "calculate",   
            "objects": [
              {   
              "database": "salesdatabase"   
              }
            ] 
          }   
        }   
      ]   
    }      
}   
```  
  
## Response  

 Returns an empty result when the command succeeds. Otherwise, an XMLA exception is returned.  
  
## Usage (endpoints)  

 This command element is used in  a statement of the Execute Method all over an XMLA endpoint, exposed in the following ways:  
  
- As an XMLA window in SQL Server Management Studio (SSMS)  
  
- As an input file to the **invoke-ascmd** PowerShell cmdlet  
  
- As an input to an SSIS task or SQL Server Agent job  
  
 You cannot generate a ready-made script  for this command from SSMS. Instead, you can start with an example or write your own.

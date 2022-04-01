---
title: "MergePartitions command (TMSL) | Microsoft Docs"
description: Use the MergePartitions command to merge the data of one or more source partitions into a target partition, and then delete the source partition.
ms.date: 04/20/2021
ms.prod: sql
ms.technology: analysis-services
ms.custom: tmsl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# MergePartitions command (TMSL)

[!INCLUDE[appliesto-sql2016-later-aas-pbip](../includes/appliesto-sql2016-later-aas-pbip.md)]

  Merges the data of one or more source partitions into a target partition, and then deletes the source partition. The SQL Query of the target partition will not be updated as part of the merge. To ensure that subsequent processing of the partition retrieves all of the data, you should revise the query so that it selects all of the data in the merged partition.  
  
## Request  

 You must specify the database, table, and source and target partitions. You can only merge partitions from the same table.  
  
```json   
{   
  "mergePartitions": {   
    "target": {   
      "database": "salesdatabase",   
      "table": "sales",   
      "partition": "may2015"   
    },   
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
}  
  
```  
  
## Response  

 Returns an empty result when the command succeeds. Otherwise, an XMLA exception is returned.  
  
## Usage (endpoints)  

 This command element is used in  a statement of the Execute Method (XMLA) call over an XMLA endpoint, exposed in the following ways:  
  
- As an XMLA window in SQL Server Management Studio (SSMS)  
  
- As an input file to the **invoke-ascmd** PowerShell cmdlet  
  
- As an input to an SSIS task or SQL Server Agent job  
  
 You can generate a ready-made script  for this command from SSMS.  For example, you can click the **Script** in Partition Management dialog box.

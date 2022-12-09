---
title: "Delete command (TMSL) | Microsoft Docs"
description: Use the Delete command to delete a database or an object in the current database and all child objects and collections.
ms.date: 04/20/2021
ms.service: analysis-services
ms.custom: tmsl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
---
# Delete command (TMSL)

[!INCLUDE[appliesto-sql2016-later-aas-pbip](../includes/appliesto-sql2016-later-aas-pbip.md)]

  Deletes a database or an object in the current database. 
It deletes the specified object and all child objects and collections. If the object does not exist, the command raises an error.  
  
## Request  

 The object being deleted is specified by using the object path. For example, deleting a partition requires that you specify the table and database objects that precede it.  
  
```json   
{   
  "delete": {   
    "object": {   
      "database": "AdventureworksDW2016",   
      "table": "Reseller Sales",   
      "partition": "may2011"   
    }   
  }   
}   
```  
  
 You can delete the following objects:  
  
 [Database object &#40;TMSL&#41;](database-object-tmsl.md)  
  
```json   
{   
  "delete": {   
    "object": {   
      "database": "AdventureworksDW2016"  
    }   
  }   
}   
```  
  
 [DataSources object &#40;TMSL&#41;](datasources-object-tmsl.md)  
  
```json   
{  
  "delete": {  
    "object": {  
      "database": "AdventureworksDW2016",  
      "dataSource": "SqlServer localhost AdventureworksDW2016"  
    }  
  }  
}  
```  
  
 [Tables object &#40;TMSL&#41;](tables-object-tmsl.md)  
  
```json   
{   
  "delete": {   
    "object": {   
      "database": "AdventureworksDW2016",   
      "table": "Reseller Sales",  
    }   
  }   
}   
```  
  
 [Partitions object &#40;TMSL&#41;](partitions-object-tmsl.md)  
  
```json   
{   
  "delete": {   
    "object": {   
      "database": "AdventureworksDW2016",   
      "table": "Reseller Sales",   
      "partition": "may2011"   
    }   
  }   
}   
```  
  
 [Roles object &#40;TMSL&#41;](roles-object-tmsl.md)  
  
```json   
{   
  "delete": {   
    "object": {   
      "database": "AdventureworksDW2016",   
      "role": "Data Reader"  
    }   
  }   
}   
```  
  
## Response  

 Returns an empty result when the command succeeds. Otherwise, an XMLA exception is returned.  
  
## Examples  

 **Example 1** - Delete a database.  
  
```json   
{  
  "delete": {  
    "object": {  
      "database": "AdventureWorksDW2016"  
    }  
  }  
}  
```  
  
 **Example 2** - Delete a connection.  
  
```json   
{  
  "delete": {  
    "object": {  
      "database": "AdventureWorksDW2016",  
      "dataSource": "SqlServer localhost AdventureworksDW2016"  
    }  
  }  
}  
```  
  
## Usage (endpoints)  

 This command element is used in  a statement of the Execute Method (XMLA) call over an XMLA endpoint, exposed in the following ways:  
  
- As an XMLA window in SQL Server Management Studio (SSMS)  
  
- As an input file to the **invoke-ascmd** PowerShell cmdlet  
  
- As an input to an SSIS task or SQL Server Agent job  
  
 You can generate a ready-made script  for this command from SSMS.  For example, you can right-click an existing database > **Script** > **Script Database as** > **DELETE To**.
---
title: "Alter command (TMSL) | Microsoft Docs"
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
# Alter command (TMSL)

[!INCLUDE[ssas-appliesto-sql2016-later-aas-pbip](../../../includes/ssas-appliesto-sql2016-later-aas-pbip.md)]

  Alters an existing object, but not its children.  If the object does not exist, the command raises an error.  
  
 Use **Alter** command for targeted updates, like setting a property on a table without having to specify all of the columns as well. This command is similar to **CreateOrReplace**, but without the requirement of having to provide a full object definition.  
  
 For objects having read-write properties, if you specify one read-write property, you will need to specify all of them, using new or existing values. You can use AMO PowerShell to get a property list. 
  
## Request  

 **Alter** does not have any attributes. Inputs include the object to be altered, followed by the modified object definition.  
  
 The following example illustrates the syntax for changing a property on a partition object. The object path establishes which partition object is to be altered via name-value pairs of parent objects. The second input is a partition object that specifies the new property value.  
  
```json  
{   
  "alter": {   
    "object": {   
      "database": "\<database-name>",   
      "table": "\<table-name>",   
      "partition": "\<partition-name>"   
    },   
    "partition": {   
      "name": "\<new-partition-name>",   
       . . .  << other properties   
    }   
  }   
}   
```  
  
 The structure of the request varies based on the object. **Alter** can be used with any of  the following objects:  
  
 [Database object &#40;TMSL&#41;](database-object-tmsl.md) Rename a database.  
  
```json   
"alter": {   
    "object": {   
      "database": "\<database-name>"  
    },   
    "database": {   
      "name": "\<new-database-name>",   
    }   
  }   
```  
  
 [DataSources object &#40;TMSL&#41;](datasources-object-tmsl.md) Rename a connection, which is a child object of database.  
  
```json   
{   
   "alter":{   
      "object":{   
         "database":"AdventureWorksTabular1200",  
         "dataSource":"SqlServer localhost AdventureworksDW2016"  
      },  
      "dataSource":{   
         "name":"A new connection name"  
      }  
   }  
}  
```  
  
 [Tables object &#40;TMSL&#41;](tables-object-tmsl.md) See **Example 1** below.  
  
 [Partitions object &#40;TMSL&#41;](partitions-object-tmsl.md) See **Example 2** below.  
  
 [Roles object &#40;TMSL&#41;](roles-object-tmsl.md) Change a property on a role object.  
  
```json   
{   
   "alter":{   
      "object":{   
         "database":"AdventureWorksTabular1200",  
         "role":"DataReader"  
      },  
      "role":{   
         "name":"New Name"  
      }  
   }  
}  
```  
  
## Response  

 Returns an empty result when the command succeeds. Otherwise, an XMLA exception is returned.  
  
## Examples  

 The following examples demonstrate script that you can run in an XMLA window in Management Studio or use as input in Invoke-ASCmd cmdlet in AMO PowerShell.  
  
 **Example 1** - This script changes the name property on a table.  
  
```json   
{   
  "alter": {   
    "object": {   
      "database": "AdventureWorksDW2016",   
      "table": "DimDate"  
    },   
    "table": {   
      "name": "DimDate2"  
    }   
  }   
}  
```  
  
 Assuming a local named instance (instance name is "tabular") and a JSON file with the alter script, this command changes a table name from DimDate to DimDate2:  
  
 `invoke-ascmd -inputfile '\\my-computer\my-shared-folder\altertablename.json' -server 'localhost\Tabular'`  
  
 **Example 2** -- This script renames a partition, for example at year end when the current year becomes the previous year. Be sure to specify all of the properties. If you leave **source** unspecified, it could break all of your existing partition definitions.  
  
 Unless you are creating, replacing, or altering the  data source object itself, any data source referenced in your script (such as in the partition script below) must be an existing **DataSource** object in your model. If you need to change the data source, do so as a separate step.  
  
```json   
{   
  "alter": {   
    "object": {   
      "database": "InternetSales",   
      "table": "DimDate",  
      "partition": "CurrentYear"  
    },   
    "partition": {   
      "name": "Year2009",  
       "source": {  
             "query":  "SELECT [dbo].[DimDate].* FROM [dbo].[DimDate] WHERE [dbo].[DimDate].CalendarYear = 2009",  
              "dataSource": "SqlServer localhost AdventureworksDW2016"  
        }  
    }   
  }   
}  
```  
  
## Usage (endpoints)  

 This command element is used in a statement of the Execute Method (XMLA) call over an XMLA endpoint, exposed in the following ways:  
  
- As an XMLA window in SQL Server Management Studio (SSMS)  
  
- As an input file to the **invoke-ascmd** PowerShell cmdlet  
  
- As an input to an SSIS task or SQL Server Agent job  
  
 You cannot generate a ready-made script  for this command from SSMS. Instead, you can start with an example or write your own.  
  
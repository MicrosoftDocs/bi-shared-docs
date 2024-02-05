---
title: "Create command (TMSL) | Microsoft Docs"
description: Use the Create command to create the specified object and all of the descendant objects that are specified.
ms.date: 04/20/2021
ms.service: analysis-services
ms.custom: tmsl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Create command (TMSL)

[!INCLUDE[appliesto-sql2016-later-aas-pbip](../includes/appliesto-sql2016-later-aas-pbip.md)]

  Creates the specified object and all of the descendant objects that are specified. If the object already exists, the command raises an error.  
  
## Request  

 The structure of the request varies based on the object. An object that is a parent must include all of its children, although the full object definitions of siblings and parent(s) are not required.  
  
 [Database object &#40;TMSL&#41;](database-object-tmsl.md) Add a database to a server.  
  
```json   
{   
  "create": {   
    "database": {   
      "name": "AdventureworksDW2016",   
      "description": "<description>"   
    }   
  }   
}  
```  
  
 [DataSources object &#40;TMSL&#41;](datasources-object-tmsl.md)  
  
```json   
{  
  "create": {  
    "parentObject": {  
      "database": "AdventureworksDW2016"  
    },  
    "dataSource": {  
      "name": "SqlServer localhost AdventureworksDW2016",  
      "connectionString": "Provider=SQLNCLI11;Data Source=localhost;Initial Catalog=AdventureworksDW2016;Integrated Security=SSPI;Persist Security Info=false",  
      "impersonationMode": "impersonateAccount",  
      "account": "<account name>",  
      "annotations": [  
        {  
          "name": "ConnectionEditUISource",  
          "value": "SqlServer"  
        }  
      ]  
    }  
  }  
}  
```  
  
 [Partitions object &#40;TMSL&#41;](partitions-object-tmsl.md) Add a partition to a parent table object.  
  
```json   
{  
  "create": {  
    "parentObject": {  
      "database": "AdventureWorksTabular1200",  
      "table": "Date"  
    },  
    "partition": {  
      "name": "Date 2",  
      "source": {  
        "query": "SELECT [dbo].[DimDate].* FROM [dbo].[DimDate]",  
        "dataSource": "SqlServer localhost AdventureworksDW2016"  
      }  
    }  
  }  
}  
```  
  
 [Roles object &#40;TMSL&#41;](roles-object-tmsl.md) Minimally add a role to a database, but without membership or filters.  
  
```json   
{  
  "create": {  
    "parentObject": {  
      "database": "AdventureWorksDW2016"  
    },  
    "role": {  
      "name": "DataReader",  
      "modelPermission": "read"  
    }  
  }  
}  
```  
  
 Except for the **Database** object, the object being created is  child of a specified **parentObject**. The parent of the **Database** object is always the **Server** object.  
  
 Server is assumed from the context. For example, if you run the script from Management Studio or AMO PowerShell, the server connection would be specified in the session or as a parameter.  
  
## Response  

 Returns an empty result when the command succeeds. Otherwise, an XMLA exception is returned.  
  
## Examples  

 **Example 1** - Add a role that specifies membership and a filter.  
  
```json   
{   
   "create":{   
      "parentObject":{   
         "database":"AdventureWorksTabular1200"  
      },  
      "role":{  
         "name":"DataReader",  
         "modelPermission":"read",  
         "members":[   
            {  
               "memberName": "account-01",  
               "memberId":"S-1-5-21-1111111111-2222222222-33333333-444444"  
            },  
            {   
               "memberName": "account-02",  
               "memberId":"S-2-5-21-1111111111-2222222222-33333333-444444"  
            }  
         ],  
         "tablePermissions":[   
            {   
               "name":"Date",  
               "filterExpression":"CalendarYear('2011')"  
            }  
         ]  
      }  
   }  
}  
```  
  
## Usage (endpoints)  

 This command element is used in  a statement of the Execute Method (XMLA) call over an XMLA endpoint, exposed in the following ways:  
  
- As an XMLA window in SQL Server Management Studio (SSMS)  
  
- As an input file to the **invoke-ascmd** PowerShell cmdlet  
  
- As an input to an SSIS task or SQL Server Agent job  
  
 You can generate a ready-made script  for this command from SSMS.  For example, you can right-click an existing database > **Script** > **Script Database as** > **CREATE To**.

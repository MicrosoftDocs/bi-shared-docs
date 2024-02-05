---
title: "Synchronize command (TMSL) | Microsoft Docs"
description: Learn about properties and usage of the Synchronize command, which synchronizes a tabular database with another existing database.
ms.date: 04/20/2021
ms.service: analysis-services
ms.custom: tmsl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Synchronize command (TMSL)

[!INCLUDE[appliesto-sql2016-later](../includes/appliesto-sql2016-later.md)]

  Synchronizes a tabular database with another existing database.  
  
## Request  

 The properties accepted by the JSON synchronize command are as follows.  
  
```json   
{   
   "synchronize":{   
      "database":"AdventureWorksDW_Production",  
      "source":"Provider=MSOLAP.7;Data Source=localhost;Integrated Security=SSPI;Initial Catalog=AdventureWorksDW_Dev",  
      "synchronizeSecurity":"copyAll",  
      "applyCompression":true  
   }  
}  
```  
  
 The properties accepted by the JSON synchronize command are as follows.  
  
| Property | Default | Description |
| -------- | ------- | ----------- |
|database||The name of the database object to be synchronized.|  
|source||The connection string to use to connect to the source server.|  
|synchronizeSecurity|skipMembership|An enumeration value that specifies how to restore security definitions, including roles and permissions. Valid values includes skipMembership, copyAll, ignoreSecurity.|  
|applyCompression|True|A Boolean that, when true, indicates that compression will be applied during the synchronization operation; otherwise false.|  
  
## Response  

 Returns an empty result when the command succeeds. Otherwise, an XMLA exception is returned.  
  
## Usage (endpoints)  

 This command element is used in  a statement of the Execute Method (XMLA) call over an XMLA endpoint, exposed in the following ways:  
  
- As an XMLA window in SQL Server Management Studio (SSMS)  
  
- As an input file to the **invoke-ascmd** PowerShell cmdlet  
  
- As an input to an SSIS task or SQL Server Agent job  
  
 You can generate a ready-made script  for this command from SSMS by clicking the Script button on the Synchronize Database dialog box.

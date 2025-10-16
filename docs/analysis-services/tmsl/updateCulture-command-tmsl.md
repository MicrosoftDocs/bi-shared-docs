---
title: "UpdateCulture command (TMSL) | Microsoft Docs"
description: Learn about properties and usage of the UpdateCulture command, which updates the culture or collation of a database.
ms.date: 10/16/2025
ms.service: analysis-services
ms.custom: tmsl
ms.topic: reference
ms.author: 
ms.reviewer: 
author: 

---
# UpdateCulture command (TMSL)

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

  Updates the culture or collation of a database.  
  
## Request  
  
```json   
{ 
   "updateCulture": {  
      "database": "AdventureWorksDW2014",  
      "culture": "en-US",  
      "collation": "Latin1_General_CI_AS"  
   }  
} 
```  
  
 The properties accepted by the JSON updateCulture command are as follows.  
  
| Property | Default | Description |
| -------- | ------- | ----------- |
|database|[Required]|The name of the database object to be updated.|  
|culture||The culture name.|  
|collation||The collation name.|  
  
## Response  

 Returns an empty result when the command succeeds. Otherwise, an XMLA exception is returned.  
  
## Usage (endpoints)  

 This command element is used in  a statement of the Execute Method (XMLA) call over an XMLA endpoint, exposed in the following ways:  
  
- As an XMLA window in SQL Server Management Studio (SSMS)  
  
- As an input file to the **invoke-ascmd** PowerShell cmdlet  
  
- As an input to an SSIS task or SQL Server Agent job  
  
 You cannot generate a ready-made script for this command from SSMS. Instead, you can start with an example or write your own.  

## Important Notes and Limitations  

 Changing the culture or collation of a semantic model is a breaking operation.  

- Across all products: Updating either setting clears the VertiPaq in-memory data store — effectively performing a full process clear. The model must be fully refreshed before it can serve queries again.  

- SQL Server Analysis Services / Azure Analysis Services: You must re-enter data source credentials for all data connections after making this change.  

- Recommendation: Always backup or save a version (Power BI) of your semantic model before modifying culture or collation.  

 This behavior is by design to ensure internal consistency of linguistic and sorting rules across all model objects.  
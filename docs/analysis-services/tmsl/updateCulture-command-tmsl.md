---
title: "UpdateCulture command (TMSL) | Microsoft Docs"
description: Learn about properties and usage of the UpdateCulture command, which updates the culture or collation of a tabular database.
ms.date: 10/16/2025
ms.service: analysis-services
ms.custom: tmsl
ms.topic: reference
ms.author: kayu
ms.reviewer: kayu
author: kayu

---
# UpdateCulture command (TMSL)

[!INCLUDE[applies-to-sql2025-later-aas-pbip](../includes/applies-to-sql2025-later-aas-pbip.md)]

  Updates the culture or collation of a tabular database at compatibility level 1200 or higher.  
  
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
  
 The updateCulture command has the following properties.  
  
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
  
 You can't generate a ready-made script for this command from SSMS. Instead, you can start with the above example.   

## Important Notes and Limitations  

 Changing the culture or collation of a semantic model is a high-impact operation.  

- Across all versions of Analysis Services: For semantic models in import mode, updating the culture or collation clears the VertiPaq in-memory data store—effectively performing a full process-clear operation. You must later perform a full data refresh to ensure consistency of linguistic and sorting rules and bring the model back into queryable state.  

- SQL Server Analysis Services / Azure Analysis Services: You must reenter data source credentials for all data connections after updating the culture or collation.  

- Always back up your semantic model before modifying the culture or collation.  

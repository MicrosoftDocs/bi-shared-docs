---
title: "Detach command (TMSL) | Microsoft Docs"
description: Learn about properties and usage of the Detach command, which detaches a tabular database from a server.
ms.date: 04/20/2021
ms.service: analysis-services
ms.custom: tmsl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Detach command (TMSL)

[!INCLUDE[appliesto-sql2016-later-aas-pbip](../includes/appliesto-sql2016-later-aas-pbip.md)]

  Detaches a tabular database from a server.  
  
## Request  
  
```json   
{   
   "detach": {    
      "database":"AdventureWorksDW2014",  
      "password": "secret"  
   }  
}  
```  
  
 The properties accepted by the JSON detach command are as follows.  
  
| Property | Default | Description |
| -------- | ------- | ----------- |
|database|[Required]|The name of the database object to be detached.|  
|password|Empty|The password to use to encrypt secrets in the detached database.|  
  
## Response  

 Returns an empty result when the command succeeds. Otherwise, an XMLA exception is returned.  
  
## Usage (endpoints)  

 This command element is used in  a statement of the Execute Method (XMLA) call over an XMLA endpoint, exposed in the following ways:  
  
- As an XMLA window in SQL Server Management Studio (SSMS)  
  
- As an input file to the **invoke-ascmd** PowerShell cmdlet  
  
- As an input to an SSIS task or SQL Server Agent job  
  
 You can generate a ready-made script  for this command from SSMS by clicking the Script button on the Detach dialog box.
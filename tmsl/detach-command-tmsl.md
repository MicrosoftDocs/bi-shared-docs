---
title: "Detach command (TMSL) | Microsoft Docs"
ms.date: 07/13/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tmsl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Detach command (TMSL)

  Detaches a tabular database from a server.  
  
## Request  
  
```  
{   
   "detach": {    
      "database":"AdventureWorksDW2014",  
      "password": "secret"  
   }  
}  
```  
  
 The properties accepted by the JSON detach command are as follows.  
  
||||  
|-|-|-|  
|**Property**|**Default**|**Description**|  
|database|[Required]|The name of the database object to be detached.|  
|password|Empty|The password to use to encrypt secrets in the detached database.|  
  
## Response  

 Returns an empty result when the command succeeds. Otherwise, an XMLA exception is returned.  
  
## Usage (endpoints)  

 This command element is used in  a statement of the [Execute Method &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-methods-execute.md) call over an XMLA endpoint, exposed in the following ways:  
  
- As an XMLA window in SQL Server Management Studio (SSMS)  
  
- As an input file to the **invoke-ascmd** PowerShell cmdlet  
  
- As an input to an SSIS task or SQL Server Agent job  
  
 You can generate a ready-made script  for this command from SSMS by clicking the Script button on the Detach dialog box.
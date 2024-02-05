---
title: "Attach command (TMSL) | Microsoft Docs"
description: Learn about properties and usage of the Attach command, which attaches a tabular database file to a server.
ms.date: 04/20/2021
ms.service: analysis-services
ms.custom: tmsl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan
---
# Attach command (TMSL)

[!INCLUDE[appliesto-sql2016-later-aas-pbip](../includes/appliesto-sql2016-later-aas-pbip.md)]

  Attaches a tabular database file to a server.  
  
## Request  
  
```json   
{   
   "attach":{   
      "folder":"C:\\Program Files\\Microsoft SQL Server\\MSAS13.Tabular\\OLAP\\Data\\",  
      "readWriteMode":"readOnly",  
      "password":"secret"  
   }  
}  
```  

 The properties accepted by the JSON attach command are as follows.  
  
| Property | Default | Description |
| -------- | ------- | ----------- |
|database|[Required]|The name of the database object to be attached.|  
|folder|[Required]|The folder that contains the attached database.|  
|password|Empty|The password to use to encrypt secrets in the attached database.|  
|readWriteMode|readWrite|An enumeration value that indicates the access modes allowed to the database.<br /><br /> **The enumeration values are as follows:**<br /><br /> readWrite – Read-write access is allowed.<br /><br /> readOnly – Read-only access is allowed.<br /><br /> readOnlyExclusive – Read-only exclusive access is allowed.|  
  
## Response 

 Returns an empty result when the command succeeds. Otherwise, an XMLA exception is returned.  
  
## Usage (endpoints)  

 This command element is used in  a statement of the Execute Method (XMLA) call over an XMLA endpoint, exposed in the following ways:  
  
- As an XMLA window in SQL Server Management Studio (SSMS)  
  
- As an input file to the **invoke-ascmd** PowerShell cmdlet  
  
- As an input to an SSIS task or SQL Server Agent job  
  
 You can generate a ready-made script  for this command from SSMS by clicking the Script button on the Attach Database dialog box.  
  

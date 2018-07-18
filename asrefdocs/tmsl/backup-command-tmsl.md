---
title: "Backup command (TMSL) | Microsoft Docs"
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
# Backup command (TMSL)

  Backs up a tabular database to an .abf backup file.  
  
## Request  
  
```  
    {  
        "backup": {  
            "description": "Parameters of Backup command of Analysis Services JSON API",  
            "properties": {  
            "database": {  
                "type": "string"  
            },  
            "file": {  
                "type": "string"  
            },  
            "password": {  
                "type": "string"  
            },  
            "allowOverwrite": {  
                "type": "boolean"  
            },  
            "applyCompression": {  
                "type": "boolean"  
            }  
            },  
. . .   
```  
  
 **Backup** has several properties.  
  
||||  
|-|-|-|  
|**Property**|**Default**|**Description**|  
|database|[Required]|The name of the database object to be backed up.|  
|file|[Required]|The backup file name/path.|  
|password|Empty|The password to use for encrypting the backup file.|  
|allowOverwrite|False|A Boolean that, when true, indicates that a backup file that already exists will be overwritten; otherwise false.|  
|applyCompression|True|A Boolean that, when true, indicates that backup files are compressed; otherwise false.|  
  
## Response  

 Returns an empty result when the command succeeds. Otherwise, an XMLA exception is returned.  
  
## Examples  

 **Example 1** - Backup a file to the default backup folder.  
  
```  
{   
   "backup": {   
      "database":"AS_AdventureWorksDW2014",  
      "file":"AS_AdventureWorksDW2014.abf",  
      "password":"secret"  
   }  
}  
```  
  
## Usage (endpoints)  

 This command element is used in  a statement of the [Execute Method &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-methods-execute.md) call over an XMLA endpoint, exposed in the following ways:  
  
- As an XMLA window in SQL Server Management Studio (SSMS)  
  
- As an input file to the **invoke-ascmd** PowerShell cmdlet  
  
- As an input to an SSIS task or SQL Server Agent job  
  
 You can generate a ready-made script  for this command from SSMS by clicking the Script button on the Backup Database dialog box.  
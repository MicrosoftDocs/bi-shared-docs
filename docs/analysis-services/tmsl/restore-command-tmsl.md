---
title: "Restore command (TMSL) | Microsoft Docs"
description: Learn about properties and usage of the Restore command, which restores a tabular database from a backup file.
ms.date: 04/20/2021
ms.service: analysis-services
ms.custom: tmsl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Restore command (TMSL)

[!INCLUDE[appliesto-sql2016-later-aas-pbip](../includes/appliesto-sql2016-later-aas-pbip.md)]

  Restores a tabular database from a backup file.  
  
## Request  
  
```json   
    {  
"restore": {  
            "description": "Parameters of Restore command of Analysis Services JSON API",  
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
            "dbStorageLocation": {  
                "type": "string"  
            },  
            "allowOverwrite": {  
                "type":boolean  
            },  
            "readWriteMode": {  
                "enum": [  
                "readWrite",  
                "readOnly",  
                "readOnlyExclusive"  
                ]  
. . .   
```  
  
 **Restore** has several properties.  
  
| Property | Default | Description |
| -------- | ------- | ----------- |
|database|[Required]|The name of the database object to be restored.|  
|file|[Required]|The backup file name/path.|  
|password|Empty|The password to use for decrypting the backup file.|  
|allowOverwrite|False|A Boolean that, when true, indicates that a backup file that already exists will be overwritten; otherwise false.|  
|readWriteMode|readWrite|An enumeration value that indicates the access modes allowed to the database.<br /><br /> **The enumeration values are as follows:**<br /><br /> readWrite – Read-write access is allowed.<br /><br /> readOnly – Read-only access is allowed.<br /><br /> readOnlyExclusive – Read-only exclusive access is allowed.|  
|dbStorageLocation|Empty|Storage location for the restored database.|  
  
## Response  

 Returns an empty result when the command succeeds. Otherwise, an XMLA exception is returned.  
  
## Example  

 **Example 1** - Restore a database from a local folder.  
  
```json   
{   
   "restore": {   
      "database":"AdventureWorksDW2014",  
      "file":"c:\\awdbdwfile.abf",  
      "security":"...",  
      "allowOverwrite":"true",  
      "password":"..",  
      "locations":"d:\\SQL Server Analysis Services\\data\\",  
      "storageLocation":".."  
   }  
}  
```  
  
## Usage (endpoints)  

 This command element is used in  a statement of the Execute Method (XMLA) call over an XMLA endpoint, exposed in the following ways:  
  
- As an XMLA window in SQL Server Management Studio (SSMS)  
  
- As an input file to the **invoke-ascmd** PowerShell cmdlet  
  
- As an input to an SSIS task or SQL Server Agent job  
  
 You can generate a ready-made script  for this command from SSMS by clicking the Script button on the Restore dialog box.
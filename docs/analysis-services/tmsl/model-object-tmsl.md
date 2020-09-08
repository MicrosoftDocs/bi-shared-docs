---
title: "Model object (TMSL) | Microsoft Docs"
description: Learn to use the Model object to define a tabular model. There is one model per database, and a Database object is the parent object.
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
# Model object (TMSL)

[!INCLUDE[ssas-appliesto-sql2016-later-aas-pbip](../includes/ssas-appliesto-sql2016-later-aas-pbip.md)]

  Defines a tabular model. There is one model per database, and only one database that can be specified in any given command. A Database object is the parent object.  
  
 Model definitions are too large to reproduce the entire syntax in one topic. For this reason, a  partial syntax highlighting the main parts can be found below, with links to child objects.  
  
 Perhaps the best way to understand a model definition is to start with a tabular model that you know well. Use the **View Code** option in SQL Server Data Tools to view its definition. Remember to install a JSON editor so that you can view the code. You can get a JSON editor in Visual Studio by [downloading the Community edition](https://www.visualstudio.com/downloads/download-visual-studio-vs.aspx) or other edition of Visual Studio.  
  
> [!NOTE]  
>  In any script, only one database at the time can be referenced. For any object other than database itself, the Database property is optional if you specify the model. There is one-to-one mapping between a Model and a Database that can be used to deduce the Database name if it's not explicitly provided.   
> Similarly, you can leave out Model, setting its properties on the Database.  
  
## Object definition  

 All objects have a common set of properties, including name, type, description, a properties collection, and annotations. **Model** objects also have the following properties.  
  
 storageLocation  
 The location on disk to place the model.  
  
 defaultMode  
 The default method for making data available in the partition.  
  
 defaultDataView  
 For models in DirectQuery mode, this property determines which partitions are used to run queries against the model.  Valid values include Full and Sample.  
  
 culture  
 The culture to use for formatting.  
  
 collation  
 The collation sequence.
  
 tables  
 The full collection of tables in the model, including partitions, columns, measures, KPIs, and annotations. See [Tables object &#40;TMSL&#41;](tables-object-tmsl.md) for details.  
  
 relationships  
 Specifies the relationship between each pair of tables, including properties that set filter direction and security. See [Relationships object &#40;TMSL&#41;](relationships-object-tmsl.md) for details.  
  
 dataSources  
 One or more connections to external databases providing data to the model or used for pass through queries. See [DataSources object &#40;TMSL&#41;](datasources-object-tmsl.md) for details.  
  
 roles  
 Objects that associate a database permission, member accounts, and optionally, security filters in DAX for custom access control.  
  
## Usage  

 **Model** objects contain an entire model. You need to specify either one Model and/or its parent Database object in most commands.  
  
 When creating, replacing, or altering a model object, specify all read-write properties of the object definition. Omission of a read-write property is considered a deletion.  
  
## Partial Syntax  

 Because this object definition is so large, only the first level properties are listed. See [Object Definitions in Tabular Model Scripting Language &#40;TMSL&#41;](tmsl-reference-tabular-objects.md) for a list of child objects.  
  
```json   
    "model": {  
      "description": "Model object of a tabular database",  
      "type": "object",  
      "properties": {  
          "name": {  },  
          "description": {  },  
         "storageLocation": {  },  
         "defaultMode":  {  },  
         "defaultDataView": {  },  
         "culture": {  },  
         "collation": {  },  
         "annotations": {  },  
         "tables": {  },  
         "relationships": {  },  
         "dataSources": {  },  
         "perspectives": {  },  
            "cultures": {  },  
         "roles": {  }  
    }  
  
```  
---
title: "Database object (TMSL) | Microsoft Docs"
description: Use the Database object to define a tabular database at compatibility level 1200 or higher, based on a model of the same level.
ms.date: 04/20/2021
ms.service: analysis-services
ms.custom: tmsl
ms.topic: reference
---
# Database object (TMSL)

[!INCLUDE[appliesto-sql2016-later-aas-pbip](../includes/appliesto-sql2016-later-aas-pbip.md)]

  Defines a tabular database at compatibility level 1200 or higher, based on a model of the same level. This topic documents the object definition of a database, providing the payload for requests that create, alter, delete, and perform database management tasks.  
  
> [!NOTE]  
>  In any script, only one database at the time can be referenced. For any object other than database itself, the Database property is optional if you specify the model. There is one-to-one mapping between a Model and a Database that can be used to deduce the Database name if it's not explicitly provided.   
> Similarly, you can leave out Model, setting its properties on the Database.  
  
## Object definition  

 All objects have a common set of properties, including name, type, description, a properties collection, and annotations. **Database** objects also have the following properties.  
  
 **compatibilitylevel**
 Currently, valid values are 1200, 1400. Lower compatibility levels use a different metadata engine.  
  
**readwritemode**
 Enumerates the mode of the database. It's common to make a database read-only in high availability or scalability configurations. Valid values include readWrite,  
                readOnly,  
                or readOnlyExclusive. 
  
## Usage  

 **Database** objects are used in almost every command. See [Commands in Tabular Model Scripting Language &#40;TMSL&#41;](tmsl-reference-commands.md) for a list. A **Database** object is a child of a Server object.  
  
 When creating, replacing, or altering a database object, specify all read-write properties of the object definition. Omission of a read-write property is considered a deletion.  
  
## Partial Syntax  

 Because this object definition is so large, only direct properties are listed. The **Model** object provides the bulk of the database definition. See [Model object &#40;TMSL&#41;](model-object-tmsl.md) to learn more about how the object is defined.  
  
```json   
    "database": {  
      "type": "object",  
      "properties": {  
        "name": {  
          "type": "string"  
        },  
        "id": {  
          "type": "string"  
        },  
        "description": {  
          "type": "string"  
        },  
        "compatibilityLevel": {  
          "type": "integer"  
        },  
        "readWriteMode": {  
          "enum": [  
            "readWrite",  
            "readOnly",  
            "readOnlyExclusive"  
          ]  
        },  
        "model": {  
          "type": "object",  
          ...  
        }  
    }  
  
```  
---
title: "Relationships object (TMSL) | Microsoft Docs"
description: Use the Relationships object to define a relationship between a source and target table, with the ability to specify cardinality.
ms.date: 04/20/2021
ms.service: analysis-services
ms.custom: tmsl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Relationships object (TMSL)

[!INCLUDE[appliesto-sql2016-later-aas-pbip](../includes/appliesto-sql2016-later-aas-pbip.md)]

  Defines a relationship between a source and target table, with the ability to specify cardinality, and the direction of query and security filters.  
  
## Object definition  

 All objects have a common set of properties, including name, type, description, a properties collection, and annotations. **Relationship** objects also have the following properties.  
  
 **isActive**  
 A Boolean that indicates whether the relationship is marked as Active or Inactive. An Active relationship is automatically used for filtering across tables. An Inactive relationship can be used explicitly by DAX calculations with the USERELATIONSHIP function.  
  
 **crossFilteringBehavior ** 
 Indicates how relationships influence filtering of data. Valid values are:  
  
- OneDirection (1) - The rows selected in the "To" end of the relationship will automatically filter scans of the table in the "From" end of the relationship.  
  
- BothDirections (2) - Filters on either end of the relationship will automatically filter the other table.  
  
- Automatic (3) - The engine will analyze the relationships and choose one of the behaviors by using heuristics.  
  
 joinOnDateBehavior  
 When joining two date time columns, indicates whether to join on date and time parts or on date part only.  
  
- DateAndTime (1) - When joining two date time columns, join on date and time parts.  
  
- DatePartOnly (2) - When joining two date time columns, join on date part only.  
  
 **relyOnReferentialIntegrity**  
 Unused; reserved for future use.  
  
 **securityFilteringBehavior**  
 An enumeration that indicates how relationships influence filtering of data when evaluating row-level security expressions. Valid values are as follows:  
  
- OneDirection (1) - The rows selected in the "To" end of the relationship will automatically filter scans of the table in the "From" end of the relationship.  
  
- BothDirections (2) - Filters on either end of the relationship will automatically filter the other table.  
  
## Usage  

 Relationship objects are used in [Alter command &#40;TMSL&#41;](alter-command-tmsl.md), [Create command &#40;TMSL&#41;](create-command-tmsl.md), [CreateOrReplace command &#40;TMSL&#41;](createorreplace-command-tmsl.md), and [Delete command &#40;TMSL&#41;](delete-command-tmsl.md).  
  
 When creating, replacing, or altering a relationship object, specify all read-write properties of the object definition. Omission of a read-write property is considered a deletion.  
  
## Full Syntax  

 Below is the schema representation of a relationship object.  
  
```json   
"relationships": {  
          "type": "array",  
          "items": {  
            "anyOf": [  
              {  
                "description": "SingleColumnRelationship object of Tabular Object Model (TOM)",  
                "type": "object",  
                "properties": {  
                  "name": {  
                    "type": "string"  
                  },  
                  "isActive": {  
                    "type": "boolean"  
                  },  
                  "type": {  
                    "enum": [  
                      "singleColumn"  
                    ]  
                  },  
                  "crossFilteringBehavior": {  
                    "enum": [  
                      "oneDirection",  
                      "bothDirections",  
                      "automatic"  
                    ]  
                  },  
                  "joinOnDateBehavior": {  
                    "enum": [  
                      "dateAndTime",  
                      "datePartOnly"  
                    ]  
                  },  
                  "relyOnReferentialIntegrity": {  
                    "type": "boolean"  
                  },  
                  "securityFilteringBehavior": {  
                    "enum": [  
                      "oneDirection",  
                      "bothDirections"  
                    ]  
                  },  
                  "fromCardinality": {  
                    "enum": [  
                      "none",  
                      "one",  
                      "many"  
                    ]  
                  },  
                  "toCardinality": {  
                    "enum": [  
                      "none",  
                      "one",  
                      "many"  
                    ]  
                  },  
                  "fromColumn": {  
                    "type": "string"  
                  },  
                  "fromTable": {  
                    "type": "string"  
                  },  
                  "toColumn": {  
                    "type": "string"  
                  },  
                  "toTable": {  
                    "type": "string"  
                  },  
                  "annotations": {  
                    "type": "array",  
                    "items": {  
                      "description": "Annotation object of Tabular Object Model (TOM)",  
                      "type": "object",  
                      "properties": {  
                        "name": {  
                          "type": "string"  
                        },  
                        "value": {  
                          "anyOf": [  
                            {  
                              "type": "string"  
                            },  
                            {  
                              "type": "array",  
                              "items": {  
                                "type": "string"  
                              }  
                            }  
                          ]  
                        }  
                      },  
                      "additionalProperties": false  
                    }  
                  }  
                },  
                "additionalProperties": false  
              }  
            ]  
          }  
        }  
```  

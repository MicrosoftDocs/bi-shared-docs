---
title: "Partitions object (TMSL) | Microsoft Docs"
description: Learn about the Partitions object, which defines a partition, or logical segmentation, of the table rowset.
ms.date: 10/20/2020
ms.service: analysis-services
ms.custom: tmsl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Partitions object (TMSL)

[!INCLUDE[appliesto-sql2016-later-aas-pbip](../includes/appliesto-sql2016-later-aas-pbip.md)]

  Defines a partition, or logical segmentation, of the table rowset. A partition consists of a Power Query M or SQL query used for importing data, for sample data in the modeling environment, or as a full data query for pass through query execution via DirectQuery.  
  
 Properties on the partition determine how the data is sourced for the table.  In the object hierarchy, the parent object of a partition is a table object.  
  
## Object definition  

 All objects have a common set of properties, including name, type, description, a properties collection, and annotations. **Partition** objects also have the following properties.  
  
 type  
 The type of partition. Valid values are numeric, and include the following:  
  
- Query (1) – data in this partition is retrieved by executing a query against a **DataSource**. The **DataSource** must be a data source defined in the model.bim file.  
  
- Calculated (2) – data in this partition is populated by executing a calculated expression.  
  
- None (3) – data in this partition is populated by pushing a rowset of data to the server as part of the Refresh operation.  
  
 mode  
 Defines the query mode of the partition. Valid values are **import**, **DirectQuery**, or **default** (inherited). This value is required.  
  
|Value|Description|  
|-|-|  
|**Import**|Indicates query requests are issued against the in-memory analytics engine storing imported data.|  
|**DirectQuery**|Pass through query execution to an external relational database. DirectQuery mode uses partitions to provide sample data used during model design. When deployed on a production server, you should switch back to Full data view. Recall that DirectQuery mode requires one partition per table, and one data source per model.|  
|**default**|Set this if you want to switch modes higher up the object tree, at the model or database level. When you choose default, the query mode will be either import or DirectQuery.|  
  
 source  
 Identifies the location of the data to be queried. Valid values are **query,calculated**, or **none**. This value is required.  
  
|Value|Description|  
|-|-|  
|**none**|Used for import mode, where data is loaded and stored in memory.|  
|**query**|For DirectQuery mode, this is a SQL query executed against the relational database specified in the model's **DataSource**. See [DataSources object &#40;TMSL&#41;](datasources-object-tmsl.md).|  
|**calculated**|Calculated tables are sourced from an expression specified when the table is created. This expression is considered the source of the partition created for the calculated table.|  
  
 dataview  
 For DirectQuery partitions, an additional dataView property further specifies whether the query that retrieves data is a sample or the full dataset. Valid values are **full**, **sample**, or **default** (inherited). As noted, samples are used only during data modeling and testing.
  
## Usage  

 Partition objects are used in [Alter command &#40;TMSL&#41;](alter-command-tmsl.md), [Create command &#40;TMSL&#41;](create-command-tmsl.md), [CreateOrReplace command &#40;TMSL&#41;](createorreplace-command-tmsl.md), [Delete command &#40;TMSL&#41;](delete-command-tmsl.md), [Refresh command &#40;TMSL&#41;](refresh-command-tmsl.md), and [MergePartitions command &#40;TMSL&#41;](mergepartitions-command-tmsl.md).  
  
 When creating, replacing, or altering a partition object, specify all read-write properties of the object definition. Omission of a read-write property is considered a deletion. Read-write properties include name, description, mode, and source.  
  
## Examples  

 **Example 1** - A simple partition structure of a table (not a fact table).  
  
```json   
"partitions": [  
          {  
            "name": "Customer",  
            "source": {  
              "query": "SELECT [dbo].[Customer].* FROM [dbo].[Customer]",  
              "dataSource": "SqlServer localhost FoodmartDB"  
            }  
]  
```  
  
 **Example 2** - Partitioned fact data is typically based on a WHERE clause that  creates non-overlapping partitions for data from the same table.  
  
```json   
"partitions": [  
          {  
            "name": "sales_fact_2015",  
            "source": {  
              "query": "SELECT [dbo].[sales_fact_2015].* FROM [dbo].[sales_fact_2015] WHERE [dbo].[sales_fact_2015].[Quarter]=4",                                                                                          
              "dataSource": "SqlServer localhost FoodmartDB"  
            },  
          }  
        ]  
```  
  
 **Example 3** - A calculated table based on a DAX expression.  
  
```json   
"partitions": [  
          {  
            "name": "CalcTable1",  
            "source": {  
              "type": "calculated",  
              "expression": "'Product Class'"  
            },  
            }  
]  
```  
  
## Full Syntax  

 Below is the schema representation of a partition object.  
  
```json   
"partitions": {  
                "type": "array",  
                "items": {  
                  "description": "Partition object of Tabular Object Model (TOM)",  
                  "type": "object",  
                  "properties": {  
                    "name": {  
                      "type": "string"  
                    },  
                    "description": {  
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
                    },  
                    "mode": {  
                      "enum": [  
                        "import",  
                        "directQuery",  
                        "default"  
                      ]  
                    },  
                    "dataView": {  
                      "enum": [  
                        "full",  
                        "sample",  
                        "default"  
                      ]  
                    },  
                    "source": {  
                      "anyOf": [  
                        {  
                          "description": "QueryPartitionSource object of Tabular Object Model (TOM)",  
                          "type": "object",  
                          "properties": {  
                            "type": {  
                              "enum": [  
                                "query",  
                                "calculated",  
                                "none"  
                              ]  
                            },  
                            "query": {  
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
                            },  
                            "dataSource": {  
                              "type": "string"  
                            }  
                          },  
                          "additionalProperties": false  
                        },  
                        {  
                          "description": "CalculatedPartitionSource object of Tabular Object Model (TOM)",  
                          "type": "object",  
                          "properties": {  
                            "type": {  
                              "enum": [  
                                "query",  
                                "calculated",  
                                "none"  
                              ]  
                            },  
                            "expression": {  
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
                      ]  
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
              },  
  
```  
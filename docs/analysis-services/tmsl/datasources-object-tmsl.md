---
title: "DataSources object (TMSL) | Microsoft Docs"
description: Use the DataSources object to define a connection to a datasource during import or in pass through queries.
ms.date: 04/20/2021
ms.prod: sql
ms.technology: analysis-services
ms.custom: tmsl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
---
# DataSources object (TMSL)

[!INCLUDE[ssas-appliesto-sql2016-later-aas-pbip](../includes/ssas-appliesto-sql2016-later-aas-pbip.md)]

Defines a connection to a datasource used by the model either during import to add data to the model, or in pass through queries via DirectQuery mode.  models in DirectQuery mode can only have one **DataSource** object.  

How the **DataSource** object is defined in a model is determined by compatibility level: 
- Tabular 1200 and lower models define a **Provider** object type. 
- Tabular 1400 and higher models typically define a **Structured** object type, however, **Provider** object type is also supported.  
  
Unless you are creating, replacing, or altering the datasource object itself, any datasource referenced in your script (such as in partition script) must be an existing **DataSource** object in your model.  

## Usage  

**DataSource** objects are used in [Alter command &#40;TMSL&#41;](alter-command-tmsl.md), [Create command &#40;TMSL&#41;](create-command-tmsl.md), [CreateOrReplace command &#40;TMSL&#41;](createorreplace-command-tmsl.md), [Delete command &#40;TMSL&#41;](delete-command-tmsl.md), [Refresh command &#40;TMSL&#41;](refresh-command-tmsl.md), and [MergePartitions command &#40;TMSL&#41;](mergepartitions-command-tmsl.md).  
  
A **DataSource** object is a property of a model, but can also be specified as a property of a Database object given the one-to-one mapping between model and Database.  Partitions based on SQL queries also specify a **DataSource**, only with a reduced set of properties.  
  
When creating, replacing, or altering a datasource object, specify all read-write properties of the object definition. Omission of a read-write property is considered a deletion.  
  
## Object definition  

Common properties for the [DataSource Object](/openspecs/sql_server_protocols/ms-ssas-t/ee12dcb7-096e-4e4e-99a4-47caeb9390f5) are described in the [MS-SSAS-T]: SQL Server Analysis Services Tabular Protocol.
 
## Syntax  

The JSON schema representation of a datasource object is defined in  [dataSource](/openspecs/sql_server_protocols/ms-ssas-t/df9b4789-6af4-4f9b-8c89-41521c05673b) object in the [MS-SSAS-T]: SQL Server Analysis Services Tabular Protocol.  

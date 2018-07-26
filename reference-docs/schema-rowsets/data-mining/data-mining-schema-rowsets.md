---
title: "Data Mining Schema Rowsets | Microsoft Docs"
ms.date: 07/25/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: schema-rowsets
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Data Mining Schema Rowsets

  A server that is running Analysis Services supports the following data mining schema rowsets. To check whether a particular XML/A provider supports a specific rowset, use the [DISCOVER_ENUMERATORS](../xml/discover-enumerators-rowset.md) rowset with the [Discover](../../xmla/xml-elements-methods-discover.md) method.  
  
 In SQL Server, the data mining schema rowsets are exposed as tables in the Transact-SQL language, in the $SYSTEM schema. For example, the following query on an Analysis Services instance returns a list of the schemas that are available on the current instance.  
  
```  
SELECT * FROM [$system].[DBSCHEMA_TABLES]  
```  
  
## In This Section  
  
|Schema Rowset|Description|  
|-------------------|-----------------|  
|[DMSCHEMA_MINING_COLUMNS Rowset](dmschema-mining-columns-rowset.md)|Describes the individual columns of all defined data mining models that are deployed on the server.|  
|[DMSCHEMA_MINING_FUNCTIONS Rowset](dmschema-mining-functions-rowset.md)|Describes the prediction functions and mining functions that can be used with each data mining algorithm that is installed on the server.|  
|[DMSCHEMA_MINING_MODEL_CONTENT Rowset](dmschema-mining-model-content-rowset.md)|Allows the client application to browse the content of a trained data mining model.|  
|[DMSCHEMA_MINING_MODEL_CONTENT_PMML Rowset](dmschema-mining-model-content-pmml-rowset.md)|Returns the XML (PMML 2.1) representation of the mining model content.|  
|[DMSCHEMA_MINING_MODEL_XML Rowset](dmschema-mining-model-xml-rowset.md)|Returns the XML (PMML 2.1) structure of the mining model. This is the same schema as DMSCHEMA_MINING_MODEL_PMML, which is preserved for backward compatibility.|  
|[DMSCHEMA_MINING_MODELS Rowset](dmschema-mining-models-rowset.md)|Enumerates the data mining models that are deployed on the server.|  
|[DMSCHEMA_MINING_SERVICE_PARAMETERS Rowset](dmschema-mining-service-parameters-rowset.md)|Provides a list of parameters that can be used to configure the behavior of each data mining algorithm that is installed on the server.|  
|[DMSCHEMA_MINING_SERVICES Rowset](dmschema-mining-services-rowset.md)|Provides a description of each data mining algorithm that is available on the server.|  
|[DMSCHEMA_MINING_STRUCTURE_COLUMNS Rowset](dmschema-mining-structure-columns-rowset.md)|Describes the individual columns of all mining structures that are deployed on the server.|  
|[DMSCHEMA_MINING_STRUCTURES Rowset](dmschema-mining-structures-rowset.md)|Enumerates information on mining structures.|  
  
 All the schema rowsets listed here are supported by the server that is running SQL Server Analysis Services.  

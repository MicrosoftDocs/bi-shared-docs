---
title: "Mining Model Properties | Microsoft Docs"
description: Learn about the kinds of properties in mining models and how you can alter them in SQL Server Analysis Services.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: data-mining
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Mining Model Properties
[!INCLUDE[appliesto-sql2019-earlier](../includes/appliesto-sql2019-earlier.md)]

[!INCLUDE[dm-dep-banner](../includes/dm-dep-banner.md)]

  Mining models have the following kinds of properties:  
  
-   Properties that are inherited from the mining structure that define the data type and content type of the data used by the model;  
  
-   Properties that are related to the algorithm used to create the mining model, including any customer parameters;  
  
-   Properties that define a filter on the model used to train the model.  
  
 The properties of a mining model are initially defined when you create the model; however, you can alter most properties later, including the algorithm parameters, filters, and column usage properties. You change properties by using the **Mining Models** tab of Data Mining Designer, or by using AMO or XMLA.  
  
 Whenever you change any property of a model, you must reprocess the model for the changes to be reflected in the model. Reprocessing is required even if the change only involves metadata, such as adding a column alias or description.  
  
## Properties of Models  
 The following table describes the properties that are specific to mining models. Additionally, there are properties that you can set on individual columns in the mining  
  
|Property|Description|  
|--------------|-----------------|  
|**Algorithm**|Sets the algorithm type for the mining model.|  
|**AlgorithmParameters**|Sets values for algorithm parameters that are available for each algorithm type.|  
|**Filter**|Sets a filter that is applied to the data that is used for training and testing the mining model. The filter definition is stored with the model and can be used optionally when you create prediction queries, or when you test the accuracy of the model.<br /><br /> The model filter is not optional when training the model.|  
|**Name**|Sets the name of the mining model.|  
|**AllowDrillThrough**|Specifies whether drill through is enabled on the mining model.|  
  
## Properties of Model Columns  
 You can set the following data mining-specific properties for each column in a mining model. You can set these properties to a different value for each mining model in a mining structure.  
  
|Property|Description|  
|--------------|-----------------|  
|**Description**|Describes the purpose of the mining column.|  
|**Name**|Sets the name of the mining model column. You can type a new name, to provide an alias for the mining model column.|  
|**ModelingFlags**|Sets any algorithm-specific flags for the column.|  
|**SourceColumnID**|Indicates the name of the mining structure column on which the model column is based.<br /><br /> This property is read-only.|  
|**Usage**|Sets how the column will be used by the mining model.|  
  
## See Also  
 [Mining Model Columns](../../analysis-services/data-mining/mining-model-columns.md)   
 [Mining Structures &#40;Analysis Services - Data Mining&#41;](../../analysis-services/data-mining/mining-structures-analysis-services-data-mining.md)   
 [Mining Model Tasks and How-tos](../../analysis-services/data-mining/mining-model-tasks-and-how-tos.md)   
 [Change the Properties of a Mining Model](../../analysis-services/data-mining/change-the-properties-of-a-mining-model.md)   
 [Data Mining Tools](../../analysis-services/data-mining/data-mining-tools.md)   
 [Create a Relational Mining Structure](../../analysis-services/data-mining/create-a-relational-mining-structure.md)   
 [Create an Alias for a Model Column](../../analysis-services/data-mining/create-an-alias-for-a-model-column.md)  
  
  

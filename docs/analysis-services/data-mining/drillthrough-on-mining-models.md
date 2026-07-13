---
title: "Drillthrough on Mining Models | Microsoft Docs"
description: Learn about options for drilling through into case data in a mining model, the ability to query a mining model to get data not exposed in the model.
ms.date: 10/31/2023
ms.service: azure-analysis-services
ms.custom: data-mining
ms.topic: concept-article

---
# Drillthrough on mining models
[!INCLUDE[appliesto-sql2019-earlier](../includes/appliesto-sql2019-earlier.md)]

[!INCLUDE[dm-dep-banner](../includes/dm-dep-banner.md)]

  *Drillthrough* is the ability to query either a mining model or a mining structure and get detailed data that the model doesn't expose.  
  
 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] provides two different options for drilling through into case data. You can drill through to the cases that you used to build the data, or you can drill through to the cases in the mining structure.  
  
## Drillthrough to model cases versus drillthrough to structure  
 Drilling through to *model cases* is useful for finding extra details about rules, patterns, or clusters in a model. For example, you don't use customer contact information for analysis in a clustering model, even if the data is available. By using drillthrough, you can access that information from the model.  
  
 In contrast, *drillthrough to structure* data provides access to information that the model doesn't make available. For example, the model might exclude some structure columns from a model because the data type is incompatible or the data isn't useful for analysis.  
  
## Enabling drillthrough on a model  
 To use drillthrough on a mining model, the following conditions must be met:  
  
-   You can configure drillthrough on just the model cases and not on the mining structure, but not vice versa. To permit drillthrough to the mining structure, you must enable drillthrough on the mining model.  
  
-   Drillthrough is disabled by default on both model and structure. If you use the Data Mining Wizard, the option to enable drillthrough to the model cases is on the final page of the wizard.  
  
-   You can add the ability to drill through on an existing mining model, but you must reprocess the model before you can drill through to the data.  
  
-   Drillthrough doesn't work unless the cache that the training process creates is preserved. For more information about the properties that control caching, see [Drillthrough on Mining Structures](../../analysis-services/data-mining/drillthrough-on-mining-structures.md).
  
## Models that support drillthrough  
 If you configure a mining model to allow drillthrough and you have the appropriate permissions, you can select a node in the viewer when you browse the model. You can retrieve detailed information about the cases in that node.  
  
 Not all models support drillthrough. Support depends on the algorithm that you use to create the model. The following table lists the types of models that don't support drillthrough, or support drillthrough with limitations. Any model types not listed here support drillthrough.  
  
|**Algorithm name**|**Support for drillthrough**|
|------------------------|----------------------------------|
|Microsoft Naïve Bayes algorithm|Not supported.<br /><br /> These algorithms don't assign cases to specific nodes in the content.|
|Microsoft Neural Network algorithm|Not supported.<br /><br /> These algorithms don't assign cases to specific nodes in the content.|
|Microsoft Logistic Regression algorithm|Not supported.<br /><br /> These algorithms don't assign cases to specific nodes in the content.|
|Microsoft Linear Regression algorithm|Supported.<br /><br /> Because the model creates a single **All** node, drillthrough returns all the training cases for the model. If the training set is large, loading the results may take a long time.|
|Microsoft Time Series algorithm|Supported.<br /><br /> However, you can't drill through to structure or case data by using the **Mining Model Viewer** in Data Mining Designer. You must create a DMX query instead.<br /><br /> Also, you cannot drill through to specific nodes, or write a DMX query to retrieve cases in specific nodes of a time series model. You can retrieve case data from either the model or the structure by using other criteria, such as date or attribute values.<br /><br /> To view details of the ARTXP and ARIMA nodes created by the Microsoft Time Series algorithm, it might be easier to use the [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](../analysis-services-overview.md?viewFallbackFrom=sql-server-ver15).|  
  
## Related tasks  
 For more information about how to use drillthrough with mining models, see the following topics.  
  
|Tasks|Links|  
|-----------|-----------|  
|Use drillthrough in the mining model viewers.|[Use Drillthrough from the Model Viewers](../../analysis-services/data-mining/use-drillthrough-from-the-model-viewers.md)|  
|Retrieve case data for a model by using drillthrough.|[Drill Through to Case Data from a Mining Model](../../analysis-services/data-mining/drill-through-to-case-data-from-a-mining-model.md)|  
|Enable drillthrough on an existing mining model.|[Enable Drillthrough for a Mining Model](../../analysis-services/data-mining/enable-drillthrough-for-a-mining-model.md)|  
|See examples of drillthrough queries for specific model types.|[Data Mining Queries](../../analysis-services/data-mining/data-mining-queries.md)|  
|Enable drillthrough in the Mining Model Wizard.|[Completing the Wizard &#40;Data Mining Wizard&#41;](../analysis-services-overview.md?viewFallbackFrom=sql-server-ver15)|  
  
## See also  
 [Drillthrough on Mining Structures](../../analysis-services/data-mining/drillthrough-on-mining-structures.md)  
  

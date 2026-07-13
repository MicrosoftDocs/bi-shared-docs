---
title: "Drillthrough on Mining Structures | Microsoft Docs"
description: Learn about options for drilling through into case data in a mining structure, the ability to query a mining structure to get data not exposed in the model.
ms.date: 10/31/2023
ms.service: azure-analysis-services
ms.custom: data-mining
ms.topic: concept-article

---
# Drillthrough on mining structures
[!INCLUDE[appliesto-sql2019-earlier](../includes/appliesto-sql2019-earlier.md)]

[!INCLUDE[dm-dep-banner](../includes/dm-dep-banner.md)]

  *Drillthrough* is the ability to query either a mining model or a mining structure and get detailed data that the model doesn't expose.  
  
 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] provides two different options for drilling through into case data. You can drill through to the data you used to build the mining model, or you can drill through to the source data in the mining structure.  
  
## Drillthrough to model cases versus drillthrough to structure  
 Drilling through to *model cases* is useful for finding extra details about rules, patterns, or clusters in a model.  
  
 In contrast, *drillthrough to structure* data provides access to information that the model doesn't make available. For example, if you have the right permissions, you can find out which rows of data were used for training the model and which rows were used for testing.  
  
 You can also view attributes of the data that weren't used in analysis, as long as they're included in the structure definition. Mining structures often support many different kinds of models, and some structure columns might be excluded from a model because the data type is incompatible or the data isn't useful for analysis. For example, you wouldn't use customer contact information in a clustering model, even if the data was included in the structure. By enabling drillthrough, you gain access to this information without running separate queries against the data source.  
  
## Enabling drillthrough to structure data  
 To use drillthrough on the mining structure, the following conditions must be met:  
  
-   Drillthrough on the model must also be enabled. By default, drillthrough of both kinds is disabled. To enable drillthrough in the Data Mining Wizard, select the option to enable drillthrough to model cases on the final page of the wizard. You can also add the ability to drillthrough on a model later by changing the **AllowDrillthrough** property.  
  
-   If you create the mining structure by using DMX, use the WITH DRILLTHROUGH clause. For more information, see [CREATE MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx).  
  
-   Drillthrough works by retrieving information about the training cases that the process cached when it processed the mining structure. Therefore, if you clear the cached data after processing the structure by changing the <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> property to **ClearAfterProcessing**, drillthrough doesn't work. To enable drillthrough to structure columns, change the <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> property to **KeepTrainingCases** and then reprocess the structure.  
  
-   Verify that both the mining structure and the mining model have the [AllowDrillThrough](../assl/properties/allowdrillthrough-element-assl.md) property set to **True**. You must also be a member of a role that has drillthrough permissions on both the structure and the model.
  
## Security issues for drillthrough  
 Set drillthrough permissions separately on the structure and model. The model permission lets you drill through from the model, even if you don't have permissions on the structure. Drillthrough permissions on the structure also give you the ability to include structure columns in drillthrough queries from the model by using the [StructureColumn (DMX)](/sql/dmx/structurecolumn-dmx) function.  
  
 For information about how to create roles and assign permissions in Analysis Services, see [Role Designer (Analysis Services - Multidimensional Data)](/previous-versions/sql/sql-server-2016/ms189696(v=sql.130)).  
  
> [!NOTE]  
>  If you enable drillthrough on both the mining structure and the mining model, any user who is a member of a role that has drillthrough permissions on the mining model can also view columns in the mining structure, even if those columns aren't included in the mining model. To protect sensitive data, set up the data source view to mask personal information, and allow drillthrough access on the mining structure only when necessary.  
  
## Related tasks  
 For more information about how to use drillthrough with mining models, see the following topics.  
  
| Task | Link |
| ---- | ---- |
|Use drillthrough to structure from the mining model viewers.|[Use Drillthrough from the Model Viewers](../../analysis-services/data-mining/use-drillthrough-from-the-model-viewers.md)|  
|See examples of drillthrough queries for specific model types.|[Data Mining Queries](../../analysis-services/data-mining/data-mining-queries.md)|  
|Get information about permissions that apply to specific mining structures and mining models.|[Grant permissions on data mining structures and models (Analysis Services)](../../analysis-services/multidimensional-models/grant-permissions-on-data-mining-structures-and-models-analysis-services.md)|  
  
## See also  
 [Drillthrough on Mining Models](../../analysis-services/data-mining/drillthrough-on-mining-models.md)  
  

---
title: "Create a Relational Mining Structure | Microsoft Docs"
description: Learn how to use the Data Mining Wizard to create a relational mining structure from relational data sources.
ms.date: 10/31/2023
ms.service: azure-analysis-services
ms.custom: data-mining
ms.topic: how-to

---
# Create a relational mining structure
[!INCLUDE[appliesto-sql2019-earlier](../includes/appliesto-sql2019-earlier.md)]

[!INCLUDE[dm-dep-banner](../includes/dm-dep-banner.md)]

  Most data mining models are based on relational data sources. When you create a relational data mining model, you can assemble ad hoc data and train and update a model without the complexity of creating a cube.  
  
 A relational mining structure can draw data from disparate sources. You can store the raw data in tables, files, or relational database systems, as long as you can define the data as part of a data source view. For example, you can use a relational mining structure if your data is in Excel, a SQL Server data warehouse or SQL Server reporting database, or in external sources that you access through the OLE DB or ODBC providers.  
  
 This article provides an overview of how to use the Data Mining Wizard to create a relational mining structure.  
  
## Requirements  
 - You must have an existing data source. If you don't have a data source, use the Data Source designer to set up a data source. For more information, see [Create a Data Source (SSAS Multidimensional)](../../analysis-services/multidimensional-models/create-a-data-source-ssas-multidimensional.md).  
  
 - Assemble the required data into a single data source view by using the Data Source View Wizard. For more information about how you can select, transform, filter, or manage data by using data source views, see [Data Source Views in Multidimensional Models](../../analysis-services/multidimensional-models/data-source-views-in-multidimensional-models.md).
  
##  <a name="BKMK_Relational_Structure"></a> Overview of process  
 Start the Data Mining Wizard by right-clicking the **Mining Structures** node in Solution Explorer and selecting **Add New Mining Structure**. The wizard guides you through the following steps to create the structure for a new relational mining model:  
  
1.  **Select the Definition Method**: Select a data source type and choose **From relational database or data warehouse**.  
  
1.  **Create the Data Mining Structure**: Determine whether to build just a structure, or a structure with a mining model.  
  
     Also choose an appropriate algorithm for your initial model. For guidance on which algorithm is best for certain tasks, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](../../analysis-services/data-mining/data-mining-algorithms-analysis-services-data-mining.md).  
  
1.  **Select Data Source View**: Choose a data sources view to use in training your model. The data source view can also contain data used for testing, or unrelated data. You can select which data is actually used in the structure and in the model. You can also apply filters to the data later.  
  
1.  **Specify Table Types**: Select the table that contains the cases used for analysis. For some data sets, especially those used for building market basket models, you might also include a related table to use as a nested table.  
  
     For each table, specify the key, so that the algorithm knows how to identify a unique record, and related records if you added a nested table.  
  
     For more information, see [Mining Structure Columns](../../analysis-services/data-mining/mining-structure-columns.md).  
  
1.  **Specify the Training Data**: Choose the *case table*, which is the table that contains the most important data for analysis.  
  
     For some data sets, especially those used for market basket models, you can also include a related table. The values in that nested table are handled as multiple values that are all related to a single row or case in the main table.  
  
1.  **Specify Columns Content and Data Types**: For each column you use in the structure, choose both a *data type* and a *content type*.  
  
     The wizard automatically detects possible data types, but you don't have to use the data type it recommends. For example, if your data contains numbers, they might represent categorical data. Columns you specify as keys are automatically assigned the correct data type for that particular model type. For more information, see [Mining Model Columns](../../analysis-services/data-mining/mining-model-columns.md) and [Data Types &#40;Data Mining&#41;](../../analysis-services/data-mining/data-types-data-mining.md).  
  
     The *content type* you choose for each column you use in the model tells the algorithm how to process the data.  
  
     For example, you might decide to discretize numbers rather than use continuous values. You can also ask the algorithm to automatically detect the best content type for the column. For more information, see [Content Types &#40;Data Mining&#41;](../../analysis-services/data-mining/content-types-data-mining.md).  
  
1.  **Create Testing Set**: Specify how much data to set aside to use in testing the model. If your data supports multiple models, it's a good idea to create a holdout data set so all models can be tested on the same data.  
  
     For more information, see [Testing and Validation &#40;Data Mining&#41;](../../analysis-services/data-mining/testing-and-validation-data-mining.md).  
  
1.  **Completing the Wizard**: Name the new mining structure and the associated mining model, and save the structure and model.  
  
     You can also set some important options, depending on the model type. For example, you can enable drillthrough on the structure.  
  
     At this point the mining structure and its model are just metadata. You need to process them both to get results.
  
##  <a name="BKMK_ChooseRelData"></a> How to choose relational data  
 You can base relational mining structures on any data that's available through an OLE DB data source. If the source data is in multiple tables, use a data source view to assemble the tables and columns you need in one place.  
  
 If the tables include any one-to-many relationships, for example you want to analyze multiple purchase records for each customer, add both tables. Then use one table as the case table, and link data on the many side of the relationship as a nested table.  
  
 The data in a mining structure comes from the existing data source view. You can modify data as needed within the data source view, adding relationships or derived columns that might not be present in the underlying relational data. You can also create named calculations or aggregations within the data source view. These features are handy if you don't have control over the arrangement of data in the data source, or if you want to experiment with different data aggregations for your models.  
  
 You don't have to use all the available data. Pick and choose which columns to include in the mining structure. All models based on that structure can use those columns, or you can flag certain columns as **Ignore** for a particular model. You can let data mining model users drill down from the results of the mining model to see mining structure columns that weren't included in the mining model itself.  
  
##  <a name="bkmk_ContentDataType"></a> How to specify content type and data type  
 The data type resembles data types you specify in SQL Server or other application interfaces: dates and times, numbers of different sizes, Boolean values, text, and other discrete data.  
  
 Content types are important for data mining and affect the outcome of analysis. The content type tells the algorithm what to do with the data. For example, should it treat numbers on a continuous scale, or bin them? How many potential values are there, and is each value distinct? If the value is a key, does the key indicate a date/time value, a sequence, or some other kind of key?  
  
 The choice of data type can limit your choice of content types. For example, you can't discretize non-numeric values. If you don't see the content type you want, select **Back** to return to the data type page and try a different data type.  
  
 Don't worry too much about choosing the right content type. It's easy to create a new model and change the content type within the model, as long as the new content type is supported by the data type set in the mining structure. It's also common to create multiple models using different content types, either as an experiment or to meet the requirements of a different algorithm.  
  
 For example, if your data contains an income column, you could create two different models when using the Microsoft Decision Trees algorithm, and configure the column alternately as either continuous numbers or discrete ranges. However, if you added a model using the Microsoft Naïve Bayes algorithm, you would have to change the column to discretized values only, because that algorithm doesn't support continuous numbers.  
  
##  <a name="bkmk_Holdout"></a> Why and how to split data into training and testing sets  
 Near the end of the wizard, you must decide whether to partition your data into training and testing sets. The ability to provision a randomly sampled portion of the data for testing is very convenient, because it ensures that a consistent set of test data is available for all models associated with the new structure.  
  
> [!IMPORTANT]  
>  This option isn't available for all model types. For example, if you create a forecasting model, you can't use holdout, because the time series algorithm requires that there be no gaps in data. For a list of the model types that support holdout data sets, see [Training and Testing Data Sets](../../analysis-services/data-mining/training-and-testing-data-sets.md).  
  
 To create the holdout data set, specify the percentage of the data you want to use for testing. All remaining data is used for training. Optionally, you can set a maximum number of cases to use for testing, or set a seed value to use in starting the random selection process.  
  
 The definition of the holdout test set is stored with the mining structure, so whenever you create a new model based on the structure, the testing data set is available for assessing the accuracy of the model. If you delete the mining structure cache, the information about which cases were used for training or testing is also deleted.
  
##  <a name="BKMK_DrillThru"></a> Why and how to enable drillthrough  
 Almost at the end of the wizard is the option to enable *drillthrough*. It's easy to miss this important option. Drillthrough lets you view source data in the mining structure by querying the mining model.  
  
 This feature is useful for viewing details. For example, if you're viewing the results of a clustering model, you might want to see the customers who are in a specific cluster. By using drillthrough, you can view details such as contact information.  
  
> [!IMPORTANT]  
>  To use drillthrough, you must enable it when you create the mining structure. You can enable drillthrough on models later by setting a property on the model, but mining structures require that you set this option at the beginning. For more information, see [Drillthrough Queries &#40;Data Mining&#41;](../../analysis-services/data-mining/drillthrough-queries-data-mining.md).  
  
## See also  
 [Data Mining Designer](../../analysis-services/data-mining/data-mining-designer.md)   
 [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](../../analysis-services/data-mining/data-mining-wizard-analysis-services-data-mining.md)   
 [Mining Model Properties](../../analysis-services/data-mining/mining-model-properties.md)   
 [Properties for Mining Structure and Structure Columns](../../analysis-services/data-mining/properties-for-mining-structure-and-structure-columns.md)   
 [Mining Structure Tasks and How-tos](../../analysis-services/data-mining/mining-structure-tasks-and-how-tos.md)  
  
  

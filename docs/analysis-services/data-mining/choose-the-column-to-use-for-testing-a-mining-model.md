---
title: "Choose the Column to Use for Testing a Mining Model | Microsoft Docs"
description: Learn how to choose the column to use for testing a mining model and how to specify the outcome to predict.
ms.date: 10/31/2023
ms.service: azure-analysis-services
ms.custom: data-mining
ms.topic: article

---
# Choose the column to use for testing a mining model
[!INCLUDE[appliesto-sql2019-earlier](../includes/appliesto-sql2019-earlier.md)]

[!INCLUDE[dm-dep-banner](../includes/dm-dep-banner.md)]

  Before you can measure the accuracy of a mining model, you must decide which outcome you want to assess. Most data mining models require that you choose at least one column to use as the predictable attribute when you create the model. Therefore, when you test the accuracy of the model, you generally must select that attribute to test.  
  
 The following list describes some additional considerations for choosing the predictable attribute to use in testing:  
  
-   Some types of data mining models can predict multiple attributes-such as neural networks, which can explore the relationships between many attributes.  
  
-   Other types of mining models, such as clustering models, don't necessarily have a predictable attribute. Clustering models can't be tested unless they have a predictable attribute.  
  
-   To create a scatter plot or measure the accuracy of a regression model, you must choose a continuous predictable attribute as the outcome. In that case, you can't specify a target value. To create anything other than a scatter plot, the underlying mining structure column must also have a content type of **Discrete** or **Discretized**.  
  
-   If you choose a discrete attribute as the predictable outcome, you can also specify a target value, or you can leave the **Predict Value** field blank. If you include a **Predict Value**, the chart measures only the model's effectiveness at predicting the target value. If you don't specify a target outcome, the model is measured for its accuracy in predicting all outcomes.  
  
-   If you want to include multiple models and compare them in a single accuracy chart, all models must use the same predictable column.  
  
-   When you create a cross-validation report, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] automatically analyzes all models that have the same predictable attribute.  
  
-   When the option **Synchronize Prediction columns and Values** is selected, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] automatically chooses predictable columns that have the same names and matching data types. If your columns don't meet these criteria, you can turn off this option and manually choose a predictable column. You might need to do this if you're testing the model with an external data set that has different columns than the model. However, if you choose a column with the wrong the type of data, you either get an error or bad results.  
  
## Specify the outcome to predict  
  
1.  Double-click the mining structure to open it in Data Mining Designer.  
  
1.  Select the **Mining Accuracy Chart** tab.  
  
1.  Select the **Input Selection** tab.  
  
1.  On the **Input Selection** tab, under **Predictable Column Name**, select a predictable column for each model that you include in the chart.  
  
     The mining model columns that are available in the **Predictable Column Name** box are only those with the usage type set to **Predict** or **Predict Only**.  
  
1.  To determine the lift for a model, select a specific outcome value to measure by choosing from the **Predict Value** list.  
  
## See also  
 [Choose and Map Model Testing Data](../../analysis-services/data-mining/choose-and-map-model-testing-data.md)   
 [Choose an Accuracy Chart Type and Set Chart Options](../../analysis-services/data-mining/choose-an-accuracy-chart-type-and-set-chart-options.md)  
  
  

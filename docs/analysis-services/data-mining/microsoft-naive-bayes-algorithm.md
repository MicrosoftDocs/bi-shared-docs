---
title: "Microsoft Naive Bayes Algorithm | Microsoft Docs"
description: Learn about the Microsoft Naive Bayes algorithm by reviewing this example in SQL Server Analysis Services.
ms.date: 10/31/2023
ms.service: azure-analysis-services
ms.custom: data-mining
ms.topic: concept-article

---
# Microsoft Naive Bayes Algorithm
[!INCLUDE[appliesto-sql2019-earlier](../includes/appliesto-sql2019-earlier.md)]

[!INCLUDE[dm-dep-banner](../includes/dm-dep-banner.md)]

  The [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes algorithm is a classification algorithm based on Bayes' theorems. You can use the algorithm for both exploratory and predictive modeling. The word naïve in the name Naïve Bayes comes from the fact that the algorithm uses Bayesian techniques but doesn't take into account dependencies that might exist.  
  
 This algorithm is less computationally intense than other [!INCLUDE[msCoName](../includes/msconame-md.md)] algorithms, and is useful for quickly generating mining models to discover relationships between input columns and predictable columns. You can use this algorithm for initial data exploration. Later, you can apply the results to create mining models with other algorithms that are more computationally intense and more accurate.  
  
## Example  
 As an ongoing promotional strategy, the marketing department for the Adventure Works Cycle company decides to target potential customers by mailing out flyers. To reduce costs, they want to send flyers only to those customers who are likely to respond. 

 The company stores information about demographics and response to a previous mailing in a database. They want to use this data to see how demographics such as age and location can help predict response to a promotion, by comparing potential customers to customers who have similar characteristics and who purchased from the company in the past. Specifically, the company wants to see the differences between customers who bought a bicycle and those who didn't.  
  
 By using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes algorithm, the marketing department can quickly predict an outcome for a particular customer profile, and therefore determine which customers are most likely to respond to the flyers. By using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes Viewer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], they can also visually investigate which input columns contribute to positive responses to flyers.
  
## How the algorithm works
 The [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes algorithm calculates the probability of every state of each input column, given each possible state of the predictable column.  
  
 To understand how this calculation works, you can use the [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes Viewer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to visually explore how the algorithm distributes states, as shown in the following graphic.  
  
 :::image type="content" source="../../analysis-services/data-mining/media/naive-bayes.png" alt-text="Screenshot of the Naive Bayes distribution of states.":::  
  
 The [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes Viewer lists each input column in the dataset, and shows how the states of each column are distributed, given each state of the predictable column. Use this view of the model to identify the input columns that are important for differentiating between states of the predictable column.  
  
 For example, in the row for **Commute Distance**, the distribution of input values is visibly different for buyers versus nonbuyers. This difference indicates that the **Commute Distance = 0-1 miles** input is a potential predictor.  
  
 The viewer also provides values for the distributions, so you can see that for customers who commute one to two miles to work, the probability of buying a bike is 0.387, and the probability they won't buy a bike is 0.287. In this example, the algorithm uses the numeric information derived from customer characteristics such as commute distance to predict whether a customer will buy a bike.  
  
 For more information about using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes Viewer, see [Browse a Model Using the Microsoft Naive Bayes Viewer](../../analysis-services/data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md).  
  
## Data required for Naive Bayes models  
 When you prepare data for training a Naive Bayes model, understand the requirements for the algorithm, including how much data it needs and how it uses the data.  
  
 The requirements for a Naive Bayes model are as follows:  
  
-   **A single key column.** Each model must contain one numeric or text column that uniquely identifies each record. Compound keys aren't allowed.  
  
-   **Input columns.** In a Naive Bayes model, all columns must either be discrete or the values must be binned. For information about how to bin or *discretize* columns, see [Discretization Methods &#40;Data Mining&#41;](../../analysis-services/data-mining/discretization-methods-data-mining.md).  
  
-   **Independent variables.** For a Naive Bayes model, the input attributes must be independent of each other. This requirement is particularly important when you use the model for prediction. If you use two columns of data that are already closely related, the effect is to multiply the influence of those columns, which can obscure other factors that influence the outcome.  
  
     Conversely, the algorithm's ability to identify correlations among variables is useful when you're exploring a model or dataset to identify relationships among inputs.  
  
-   **At least one predictable column.** The predictable attribute must contain discrete or discretized values.  
  
     You can treat the values of the predictable column as inputs. This practice can be useful when you're exploring a new dataset to find relationships among the columns.  
  
## Viewing the model  
 To explore the model, use the **Microsoft Naive Bayes Viewer**. The viewer shows how the input attributes relate to the predictable attribute. The viewer also provides a detailed profile of each cluster, a list of the attributes that distinguish each cluster from the others, and the characteristics of the entire training data set. For more information, see [Browse a Model Using the Microsoft Naive Bayes Viewer](../../analysis-services/data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md).  
  
 For more detail, browse the model in the [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](../analysis-services-overview.md?viewFallbackFrom=sql-server-ver15). For more information about the type of information stored in the model, see [Mining Model Content for Naive Bayes Models &#40;Analysis Services - Data Mining&#41;](../../analysis-services/data-mining/mining-model-content-for-naive-bayes-models-analysis-services-data-mining.md).  
  
## Making predictions  
 After you train the model, it stores the results as a set of patterns that you can explore or use to make predictions. You can create queries to return predictions about how new data relates to the predictable attribute, or you can retrieve statistics that describe the correlations the model found.  
  
 For information about how to create queries against a data mining model, see [Data Mining Queries](../../analysis-services/data-mining/data-mining-queries.md). For examples of how to use queries with a Naive Bayes model, see [Naive Bayes Model Query Examples](../../analysis-services/data-mining/naive-bayes-model-query-examples.md).  
  
## Remarks  
  
-   Supports the use of Predictive Model Markup Language (PMML) to create mining models.  
  
-   Supports drillthrough.  
  
-   Doesn't support the creation of data mining dimensions.
  
-   Supports the use of OLAP mining models.  
  
## See also  
 [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](../../analysis-services/data-mining/data-mining-algorithms-analysis-services-data-mining.md)   
 [Feature Selection &#40;Data Mining&#41;](../../analysis-services/data-mining/feature-selection-data-mining.md)   
 [Naive Bayes Model Query Examples](../../analysis-services/data-mining/naive-bayes-model-query-examples.md)   
 [Mining Model Content for Naive Bayes Models &#40;Analysis Services - Data Mining&#41;](../../analysis-services/data-mining/mining-model-content-for-naive-bayes-models-analysis-services-data-mining.md)   
 [Microsoft Naive Bayes Algorithm Technical Reference](../../analysis-services/data-mining/microsoft-naive-bayes-algorithm-technical-reference.md)  
  

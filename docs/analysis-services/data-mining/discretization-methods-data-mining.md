---
title: "Discretization Methods (Data Mining) | Microsoft Docs"
description: Learn how to discretize data in a mining model, which involves putting values into buckets so that there are a limited number of possible states.
ms.date: 10/31/2023
ms.service: azure-analysis-services
ms.custom: data-mining
ms.topic: concept-article

---
# Discretization methods (data mining)
[!INCLUDE[appliesto-sql2019-earlier](../includes/appliesto-sql2019-earlier.md)]

[!INCLUDE[dm-dep-banner](../includes/dm-dep-banner.md)]

  Some algorithms that create data mining models in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] require specific content types to function correctly. For example, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes algorithm can't use continuous columns as input and can't predict continuous values. Also, some columns contain so many values that the algorithm can't easily identify interesting patterns in the data to create a model from.  
  
 In these cases, you can discretize the data in the columns to enable using the algorithms to produce a mining model. *Discretization* is the process of putting values into buckets so there are a limited number of possible states. The buckets themselves are treated as ordered and discrete values. You can discretize both numeric and string columns.  
  
 Several methods are available to discretize data. If your data mining solution uses relational data, you can control the number of buckets to use for grouping data by setting the value of the <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> property. The default number of buckets is 5.  
  
 If your data mining solution uses data from an Online Analytical Processing (OLAP) cube, the data mining algorithm automatically computes the number of buckets to generate by using the following equation, where `n` is the number of distinct values of data in the column:  
  
 `Number of Buckets = sqrt(n)`  
  
 If you don't want [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to calculate the number of buckets, use the <xref:Microsoft.AnalysisServices.DimensionAttribute.DiscretizationBucketCount%2A> property to manually specify the number of buckets.  
  
 The following table describes the methods you can use to discretize data in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].  
  
|Discretization method|Description|  
|---------------------------|-----------------|  
|**AUTOMATIC**|[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] determines which discretization method to use.|  
|**CLUSTERS**|The algorithm divides the data into groups by sampling the training data, initializing to a number of random points, and then running several iterations of the Microsoft Clustering algorithm using the Expectation Maximization (EM) clustering method. The **CLUSTERS** method is useful because it works on any distribution curve. However, it requires more processing time than the other discretization methods.<br /><br /> This method can be used only with numeric columns.|  
|**EQUAL_AREAS**|The algorithm divides the data into groups that contain an equal number of values. This method is best used for normal distribution curves, but doesn't work well if the distribution includes a large number of values in a narrow group in the continuous data. For example, if one-half of the items have a cost of 0, one-half the data occurs under a single point in the curve. In such a distribution, this method breaks up the data in an effort to establish equal discretization into multiple areas. This process produces an inaccurate representation of the data.|
  
## Remarks  
  
-   Use the **EQUAL_AREAS** method to discretize strings.
  
-   The **CLUSTERS** method uses a random sample of 1,000 records to discretize data. Use the **EQUAL_AREAS** method if you don't want the algorithm to sample data.

  
  
  
## See also  
 [Content Types &#40;Data Mining&#41;](../../analysis-services/data-mining/content-types-data-mining.md)   
 [Content Types &#40;DMX&#41;](/sql/dmx/content-types-dmx)   
 [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](../../analysis-services/data-mining/data-mining-algorithms-analysis-services-data-mining.md)   
 [Mining Structures &#40;Analysis Services - Data Mining&#41;](../../analysis-services/data-mining/mining-structures-analysis-services-data-mining.md)   
 [Data Types &#40;Data Mining&#41;](../../analysis-services/data-mining/data-types-data-mining.md)   
 [Mining Structure Columns](../../analysis-services/data-mining/mining-structure-columns.md)   
 [Column Distributions &#40;Data Mining&#41;](../../analysis-services/data-mining/column-distributions-data-mining.md)  
  
  

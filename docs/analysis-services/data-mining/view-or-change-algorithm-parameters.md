---
title: "View or Change Algorithm Parameters | Microsoft Docs"
description: Learn how to change the parameters in algorithms that you use to build data mining models to customize the results of the model in SQL Server Analysis Services.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: data-mining
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# View or Change Algorithm Parameters
[!INCLUDE[appliesto-sql2019-earlier](../includes/appliesto-sql2019-earlier.md)]

[!INCLUDE[dm-dep-banner](../includes/dm-dep-banner.md)]

  You can change the parameters provided with the algorithms that you use to build data mining models to customize the results of the model.  
  
 The algorithm parameters provided in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] change much more than just properties on the model: they can be used to fundamentally alter the way that data is processed, grouped, and displayed. For example, you can use algorithm parameters to do the following:  
  
-   Change the method of analysis, such as the clustering method.  
  
-   Control feature selection behavior.  
  
-   Specify the size of itemsets or the probability of rules.  
  
-   Control branching and depth of decision trees.  
  
-   Specify a seed value or the size of the internal holdout set used for model creation.  
  
 The parameters provided for each algorithm vary greatly; for a list of the parameters that you can set for each algorithm, see the technical reference topics in this section: [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](../../analysis-services/data-mining/data-mining-algorithms-analysis-services-data-mining.md).  
  
### Change an algorithm parameter  
  
1.  On the **Mining Models** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], right-click the algorithm type of the mining model for which you want to tune the algorithm, and select **Set Algorithm Parameters**.  
  
     The **Algorithm Parameters** dialog box opens.  
  
2.  In the **Value** column, set a new value for the algorithm that you want to change.  
  
     If you do not enter a value in the **Value** column, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses the default parameter value. The **Range** column describes the possible values that you can enter.  
  
3.  Click **OK**.  
  
     The algorithm parameter is set with the new value. The parameter change will not be reflected in the mining model until you reprocess the model.  
  
### View the parameters used in an existing model  
  
1.  In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open a DMX Query window.  
  
2.  Type a query like this one:  
  
    ```  
    select MINING_PARAMETERS   
    from $system.DMSCHEMA_MINING_MODELS  
    WHERE MODEL_NAME = '<model name>'  
  
    ```  
  
## See Also  
 [Mining Model Tasks and How-tos](../../analysis-services/data-mining/mining-model-tasks-and-how-tos.md)  
  
  

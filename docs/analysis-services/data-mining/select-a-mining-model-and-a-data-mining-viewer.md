---
title: "Select a Mining Model and a Data Mining Viewer | Microsoft Docs"
description: Learn how to explore a mining model by using a viewer in Data Mining Designer in SQL Server Analysis Services.
ms.date: 02/14/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: data-mining
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Select a Mining Model and a Data Mining Viewer
[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]

[!INCLUDE[dm-dep-banner](../includes/dm-dep-banner.md)]

  You can explore a mining model by using one of the viewers on the **Mining Model Viewer** tab of Data Mining Designer. You can easily switch between models, or change the viewer that is used.  
  
-   The **Mining Model** drop-down list box on the **Mining Model Viewer** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] contains a list of all the mining models that are in the current mining structure.  
  
-   Custom viewers are provided for each type of model. For an overview of all the custom viewers, see [Mining Model Viewers &#40;Data Mining Model Designer&#41;](../analysis-services-overview.md?viewFallbackFrom=sql-server-ver15). For a walkthrough of how to use the custom viewers to understand a model, see [Lesson 4: Exploring the Targeted Mailing Models &#40;Basic Data Mining Tutorial&#41;](/previous-versions/sql/sql-server-2016/ms166930(v=sql.130)).  
  
-   The [!INCLUDE[msCoName](../includes/msconame-md.md)] Generic Content Viewer shows the patterns discovered by the algorithm in a standard representation of nodes in a tree. Although the generic tree view shows all the content for the model in rich detail, it is more difficult to interpret. For more information, see [Browse a Model Using the Microsoft Generic Content Tree Viewer](../../analysis-services/data-mining/browse-a-model-using-the-microsoft-generic-content-tree-viewer.md).  
  
### To select a viewer type  
  
-   Select the viewer that is provided for the specific type of model that you created, using the **Viewer** list at the top of the **Mining Model Viewer** tab.  
  
-   Or, use the **Microsoft Generic Mining Content Viewer**  
  
### To select a mining model to view  
  
-   On the **Mining Model Viewer** tab in Data Mining Designer, select the mining model that you want to view from the **Mining Model** list.  
  
 The selected mining model opens in the viewer that is provided for that model type.  
  
## See Also  
 [Mining Model Viewer Tasks and How-tos](../../analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md)  
  

---
title: "Find a Specific Node in a Dependency Network | Microsoft Docs"
description: Find a specific node in a dependency network in a mining model by using the Find Node dialog box in Data Mining Designer in SQL Server Analysis Services.
ms.date: 02/14/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: data-mining
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Find a Specific Node in a Dependency Network
[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]

[!INCLUDE[dm-dep-banner](../includes/dm-dep-banner.md)]

  A dependency network in a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] mining model can contain many nodes, making it difficult to locate the data you are interested in. To solve this problem, you can use the **Find Node** dialog box on the **Dependency Network** tab of Data Mining Designer to search for a specific node.  
  
### To find a specific node in a dependency network  
  
1.  On the **Mining Model Viewer** tab of **Data Mining Designer** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Find Node** on the toolbar of the **Dependency Network** tab of the mining model viewer.  
  
     The **Find Node** dialog box opens.  
  
2.  In the **Node name contains** box, enter part of the name of the node for which you want to search.  
  
     The list of nodes is filtered to display only those nodes that contain part of the search path.  
  
3.  Select the correct node from the list, and then click **OK**.  
  
## See Also  
 [Mining Model Viewer Tasks and How-tos](../../analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md)  
  
  

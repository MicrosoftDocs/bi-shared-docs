---
title: "Add a Mining Model to an Existing Mining Structure | Microsoft Docs"
description: Learn how to add a mining model to an existing mining structure and to define the usage of the columns differently for each mining model.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: data-mining
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Add a Mining Model to an Existing Mining Structure
[!INCLUDE[appliesto-sql2019-earlier](../includes/appliesto-sql2019-earlier.md)]

[!INCLUDE[dm-dep-banner](../includes/dm-dep-banner.md)]

  You can add more mining models to a mining structure, after you add the initial model. Each model must contain columns that exist in the structure, but you can define the usage of the columns differently for each mining model. For more information about how to define mining models columns, see [Mining Model Columns](../../analysis-services/data-mining/mining-model-columns.md).  
  
### To add a mining model to the structure  
  
1.  From the **Mining Model** menu item in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], select **New Mining Model**.  
  
     The **New Mining Model** dialog box opens.  
  
2.  Under **Model name**, enter a name for the new mining model.  
  
3.  Under **Algorithm name**, select the algorithm that the mining model will be built from.  
  
4.  Click **OK**.  
  
 A new mining model appears in the **Mining Models** tab. The model uses the default columns that exist in the structure. For information about how to modify the columns, see [Change the Properties of a Mining Model](../../analysis-services/data-mining/change-the-properties-of-a-mining-model.md).  
  
## See Also  
 [Mining Model Tasks and How-tos](../../analysis-services/data-mining/mining-model-tasks-and-how-tos.md)  
  
  

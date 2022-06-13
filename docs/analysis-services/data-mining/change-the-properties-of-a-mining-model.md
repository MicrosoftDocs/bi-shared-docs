---
title: "Change the Properties of a Mining Model | Microsoft Docs"
description: In this article, learn how to change the properties of a mining model and mining model column.
ms.date: 02/14/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: data-mining
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Change the Properties of a Mining Model
[!INCLUDE[appliesto-sql2019-earlier](../includes/appliesto-sql2019-earlier.md)]

[!INCLUDE[dm-dep-banner](../includes/dm-dep-banner.md)]

  Some mining model properties apply to the model as a whole, and other model properties apply to individual columns. Examples of properties that apply to the entire model would be the **Drillthrough** property, which specifies whether the case data should be available for querying, and the **Description** property. Properties that apply to the column include **Usage** and **ModelingFlags**, which control how data in the column is used within the model.  
  
 The following model properties have advanced editors that you can use to create expressions or configure complex model properties. The following properties provide:  
  
-   **Filter** property: Opens the [Data Set Filter or Model Filter Dialog Box](../analysis-services-overview.md?viewFallbackFrom=sql-server-ver15).  
  
-   **AlgorithmParameters** property: Opens the [Algorithm Parameters Dialog Box &#40;Mining Models View&#41;](../analysis-services-overview.md?viewFallbackFrom=sql-server-ver15).  
  
 For information about how to set the properties in a mining model, see [Mining Model Columns](../../analysis-services/data-mining/mining-model-columns.md).  
  
### To change the properties of a mining model  
  
1.  In the **Mining Models** tab in Data Mining Designer, right-click either the column header that contains the name of the mining model, or the row in the grid that contains the name of the mining algorithm, and then select **Properties**.  
  
2.  In the **Properties** window on the right side of the screen, highlight the value that corresponds to the property that you want to change, and enter the new value.  
  
     The new value will take effect when you select a different element in the designer.  
  
### To change the properties of a mining model column  
  
1.  In the **Mining Models** tab in Data Mining Designer, right-click the cell in the grid at the intersection of the mining structure column and the mining model, and then select **Properties**.  
  
2.  In the **Properties** window on the right side of the screen, highlight the value that corresponds to the property that you want to change, and enter the new value.  
  
    > [!NOTE]  
    >  If the column usage is set to **Ignore**, the **Properties** window for the column is blank.  
  
     The new value will take effect when you select a different element in the designer.  
  
## See Also  
 [Mining Model Tasks and How-tos](../../analysis-services/data-mining/mining-model-tasks-and-how-tos.md)  
  

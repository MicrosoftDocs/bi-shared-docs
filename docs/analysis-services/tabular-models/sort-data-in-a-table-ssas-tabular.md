---
title: "Sort data in an Analysis Services tabular model table | Microsoft Docs"
description: Learn how to sort data in an Analysis Services tabular model table based on a text column.
ms.date: 01/29/2020
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Sort Data in a Table

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

  You can sort data by text (A to Z or Z to A) and numbers (smallest to largest or largest to smallest) in one or more columns.  
  
### To sort the data in a table based on a text column  
  
1.  In the model designer, select a column of alphanumeric data, a range of cells in a column, or make sure that the active cell is in a table column that contains alphanumeric data, and then click the arrow in the header of the column that you want to filter by.  
  
2.  In the AutoFilter menu, do one of the following:  
  
    -   To sort in ascending alphanumeric order, click **Sort A to Z**.  
  
    -   To sort in descending alphanumeric order, click **Sort Z to A**.  
  
    > [!NOTE]  
    >  In some cases, data imported from another application might have leading spaces inserted before data. You must remove the leading spaces in order to correctly sort the data.  
  
### To sort the data in a table based on a numeric column  
  
1.  In the model designer, select a column of alphanumeric data, a range of cells in a column, or make sure that the active cell is in a table column that contains alphanumeric data, and then click the arrow in the header of the column that you want to filter by.  
  
2.  In the AutoFilter menu, do one of the following:  
  
    -   To sort from low numbers to high numbers, click **Sort Smallest to Largest**.  
  
    -   To sort from high numbers to low numbers, click **Sort Largest to Smallest**.  
  
    > [!NOTE]  
    >  If the results are not what you expected, the column might contain numbers stored as text and not as numbers. For example, negative numbers imported from some accounting systems, or a number entered with a leading ' (apostrophe), are stored as text.  
  
## See Also  
 [Filter and Sort Data](?viewFallbackFrom=sql-server-ver15)   
 [Perspectives](../../analysis-services/tabular-models/perspectives-ssas-tabular.md)   
 [Roles](../../analysis-services/tabular-models/roles-ssas-tabular.md)  
  

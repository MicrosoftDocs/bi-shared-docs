---
title: "Delete a column in an Analysis Services tabular model | Microsoft Docs"
description: Learn how to delete a column in an Analysis Services tabular model.
ms.date: 01/29/2020
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Delete a Column

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]
  This article describes how to delete a column from a tabular model table.  
  
## Delete a Model Table Column  
  
> [!NOTE]  
>  Deleting a column from a model table does not delete the column from a partition query definition. If the column you are deleting is part of a partition, you must manually delete the column from the partition query definition. Failure to delete the column from the partition query definition will cause the column to be queried and data returned, but not populated to the model table, during processing operations. For more information, see [Partitions](../../analysis-services/tabular-models/partitions-ssas-tabular.md).  
  
#### To delete a model table column  
  
-   In the model designer, in the table that contains the column you want to delete, right-click on the column, and then click **Delete**.  
  
#### To delete a model table column by using the Table Properties dialog box  
  
1.  In the model designer, click on the table which contains the column you want to delete, then click the **Table** menu, and then click  **Table Properties**.  
  
2.  In **Column names from**, select **Model** (*to use model table column names, if different from source*).  
  
3.  In the **Edit Table Properties** dialog box, in the table preview window, uncheck the column you want to delete, and then click **OK**.  
  
## See Also  
 [Add columns to a table](../../analysis-services/tabular-models/add-columns-to-a-table-ssas-tabular.md)   
 [Partitions](../../analysis-services/tabular-models/partitions-ssas-tabular.md)  
  
  

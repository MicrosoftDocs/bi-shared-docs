---
title: "Delete a table in an Analysis Services tabular model | Microsoft Docs"
description: Learn how to use the model designer to delete a table in Analysis Services tabular model.
ms.date: 01/29/2020
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Delete a table

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

  In the model designer, you can delete tables in your model workspace database that you no longer need. Deleting a table does not affect the original source data, only the data that you imported and were working with. You cannot undo the deletion of a table.  
  
### To delete a table  
  
-   Right-click the tab at the bottom of the model designer for the table that you want to delete, and then click **Delete**.  
  
## Considerations when Deleting Tables  
  
-   When you delete a table, the entire tab that the table was on is deleted.  
  
-   If any measures were associated with that table, the definition of the measure will also be deleted.  
  
-   If you created any calculated columns using that table, columns in that table are also deleted; any calculated columns in other tables that use columns from the deleted table will display an error.  
  
## See also  
 [Tables and columns](../../analysis-services/tabular-models/tables-and-columns-ssas-tabular.md)  
  
  

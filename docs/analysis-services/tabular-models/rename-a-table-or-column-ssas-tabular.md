---
title: "Rename an Analysis Services tabular model table or column | Microsoft Docs"
description: Learn how to rename a column or table during the Get Data\import process in Power Query Editor.
ms.date: 07/15/2020
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Rename a table or column

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

You can rename a column or table during the Get Data\import process in Power Query Editor.
  
After you've imported data to the model, the name (or title) of a table appears on the table tab, at the bottom of the model designer. You can change the name of your table to give it a more appropriate name. You can also rename a column after the data has been added to the model. This option is especially important when you have imported data from multiple sources, and want to ensure that columns in different tables have names that are easy to distinguish.  
  
## To rename a table
  
1. In the model designer, right-click the tab that contains the table that you want to rename, and then click **Rename**.  
  
2. Type the new name.  
  
    > [!NOTE]  
    >  You can edit other properties of a table, including the connection information and column mappings, by using the **Edit Table Properties** dialog box. However, you cannot change the name in this dialog box.  
  
## To rename a column  
  
1. In the model designer, double-click the header of the column that you want to rename, or right-click the header and select **Rename Column** from the context menu.  
  
2. Type the new name.  
  
## Naming Requirements for columns and tables

 The following words and characters cannot be used in the name of a table or column:  
  
- Leading or trailing spaces  
  
- Control characters  
  
- The following characters (which are not valid in the names of Analysis Services objects): .,;':/\\*|?&%$!+=()[]{}<>  
  
- Analysis Services reserved keywords, including Multidimensional Expressions (MDX) and Data Mining Extensions (DMX) function names and operators.  
  
## Effect of renaming on existing tables, columns, and calculations

 Whenever you change the name of a table, you change the name of the underlying table object, which may contain multiple columns or measures. Any columns that are in the table, and any relationships that use the table, must be updated to use the new name in their definitions. This update happens automatically in most cases.
  
 Any calculations that use the renamed table, or that use columns from the renamed table, must also be updated, and the data derived from those calculations must be refreshed and recalculated. Depending on how many tables and calculations are affected, this can take some time to complete. Therefore, the best time to rename tables is either during the import process, or before you start to build complex relationships and calculations.  
  
## See also

 [Tables and Columns](../../analysis-services/tabular-models/tables-and-columns-ssas-tabular.md)  
 [Import from Power Pivot](../../analysis-services/tabular-models/import-from-power-pivot-ssas-tabular.md)  
 [Import from Analysis Services](../../analysis-services/tabular-models/import-from-analysis-services-ssas-tabular.md)  
  
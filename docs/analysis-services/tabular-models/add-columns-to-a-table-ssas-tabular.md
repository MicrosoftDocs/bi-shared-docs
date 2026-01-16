---
title: "Add columns to an Analysis Services tabular model table | Microsoft Docs"
description: Learn how to add columns to an Analysis Services tabular model table.
ms.date: 03/12/2020
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: how-to
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Add columns to a table

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]
  This article describes how to add columns to an existing table.  
  
## Add columns from the datasource

 When using the Get Data to import data from a structured data source table, a new table is created in the model which includes all of the columns in the source table, or if you choose to filter out certain columns by using the Transform feature, only those columns and filtered data you select. You can also write a Power Query M expression that specifies only certain columns to import. You may, however, later determine a source table has additional columns that you want to add to the model table, or you need to add a calculated column with values derived from a DAX formula.  
  
 If, for example, when you initially imported from a data source, you used the Transform feature to select a limited number of columns from the source table, you later determine that you need to add another column that exists at the source table, but does not yet exist in the model table. Or, for example, a new AdjustedProfit column was added to the FactSales table at the data source, and you now want to add the same AdjustedProfit column and data to the Sales table in the model.  
  
 In these cases, you can use Power Query Editor to select columns from the source table and add them to the model table. 
  
> [!IMPORTANT]  
>  When adding a column to a table that contains two or more partitions, before adding the column to the table definition by using the Edit Table Properties dialog box, you must first use Partition Manager to add the column to all defined partitions. After you have added the column to the defined partitions, you can then add the same column to the table definition by using the Edit Table Properties dialog box.  
  
> [!NOTE]  
>  If you used a custom M expression to select tables and columns when you initially used the Power Query Editor to import data, you must again use an M expression.  
  
#### To add a column from the data source by using the Edit Table Properties dialog box
  
1.  In the Power, click on the table you want to add a column to, then click the **Extensions** > **Table** > **Table Properties**.  
  
2.  In the **Edit Table Properties** dialog box, edit the M expression or click **Design**. In the Power Query Editor, select the source column you want to add, and then click **Import**.
  
## Add a calculated column
 In a calculated column, a DAX formula is used to define a value for each row. For example, you can create a calculated column with a simple formula (=1) that adds a value of 1 to each row. Calculated columns can also have more complex formulas that calculate values based on other data in the model. Calculated columns are covered in more detail in other topics. For more information, see [Calculated Columns](../../analysis-services/tabular-models/ssas-calculated-columns.md).  
  
#### To create a calculated column
  
1.  In the model designer, in Data View, select the table to which you want to add a new, blank calculated column, scroll to the right-most column, or click the **Column** menu, and then click **Add Column**.  
  
     To create a new column between two existing columns, right-click on an existing column, and then click **Insert Column**.  
  
2.  In the formula bar, type a DAX formula to add attributes for each row.  
  
## Add a blank column

 You can create a named, blank column in a model table. Blank columns can be useful if you want to paste data from another source. Keep in-mind that pasted data is stored differently than imported data.  
  
#### To create a named, blank column
  
1.  In the model designer, in Data View, select the table to which you want to add a blank column, scroll to the right-most column, or click the **Column** menu, and then click **Add Column**.  
  
     To create a new column between two existing columns, right-click an existing column, and then click **Insert Column**.  
  
2.  Click on the top cell, then type a name, and then press ENTER.  
  
## See also

 [Edit table properties dialog box](../analysis-services-overview.md?viewFallbackFrom=sql-server-ver15)   
 [Change table, column, or row filter mappings](../../analysis-services/tabular-models/change-table-column-or-row-filter-mappings-ssas-tabular.md)  
  

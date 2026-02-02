---
title: "Add a table to an Analysis Services tabular model | Microsoft Docs"
description: Learn how to add a table from a structured data source from which you have previously imported data into your model.
ms.date: 03/12/2020
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: how-to
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Add a table

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

  This article describes how to add a table from a structured data source from which you have previously imported data into your model. To add a table from the same data source, you can use the existing data source connection. It is recommended you always use a single connection when importing any number of tables from a single data source.  
  
### To add a table from an existing data source
  
1.  In **Tabular Model Explorer**, expand **Data Sources**, right-click a data source, and then click **Import new tables**.  
  
2.  In **Navigator**, select the table you want to add to your model.  
  
    > [!NOTE]  
    >  Navigator does not show tables that were previously imported as checked. If you select a table that was previously imported using this connection, and you did not give the table a different friendly name, a 1 is appended to the friendly name. You do not need to re-select any tables that were previously imported by using this connection.  
  
3.  If necessary, use **Transform Data** to select only certain columns or apply filters to the data to be imported.  
  
4.  Click **Load** to import the new table.  
  
> [!NOTE]  
>  When importing multiple tables at the same time from a single data source, any relationships between those tables at the source are automatically be created in the model. When adding a table later; however, you may need to manually create relationships in the model between newly added tables and the tables that were previously imported.  
  
  
  

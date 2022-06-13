---
title: "Import data by using a native query (Analysis Services) | Microsoft Docs"
description: Learn how to create a connection to a datasource and then create a native SQL query to specify data import.
ms.date: 06/10/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2017"
---
# Import data by using a native query

[!INCLUDE[appliesto-sql2017-later-aas-pbip](../includes/appliesto-sql2017-later-aas-pbip.md)]

For tabular 1400 and higher models, the new Get Data experience in Visual Studio Analysis Services projects provides immense flexibility in how you can mashup your data during import. This article describes creating a connection to a data source and then creating a native SQL query to specify data import.

## Create a data source connection

If you don't already have a connection to your data source, you need to create one.

1. In Visual Studio > **Tabular Model Explorer**, right-click **Data Sources**, and then click **New Data Source**.
2. In **Get Data**, select your datasource type, and then click **Connect**. Follow any additional steps required to connect to your data source.

## Enter a query as a named expression

1. In **Tabular Model Explorer**, right-click **Expressions** > **Edit Expressions**.
2. In **Query Editor**, click **Query** > **New Query** > **Blank Query**
3. In the formula bar, type
    ```
    = Value.NativeQuery(#"DATA SOURCE NAME", "SELECT * FROM ...")
    ```
4. To create a table, in **Queries**, right-click the query, and then select **Create New Table**. The new table will have the same name as the query.

## Example

This native query creates an Employee table in the model that includes all columns from the Dimension.Employee table at the data source.

```
= Value.NativeQuery(#"SQL/myserver;WideWorldImportersDW", "SELECT * FROM Dimension.Employee")
```
![Query editor](media/ssas-import-query-example.png)


After importing, a table named Employees is created in the model.   

![Table in Tabular Model Explorer](media/ssas-import-query-example-table.png)

## See also  

 [Impersonation](../../analysis-services/tabular-models/impersonation-ssas-tabular.md)   

  

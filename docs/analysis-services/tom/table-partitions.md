---
title: "Use hot and cold table partitions to optimize very large Power BI data models"
description: Learn how to use hot and cold table partitions to optimize very large data models in Analysis Services Management Objects (AMO) Tabular Object Model (TOM).
ms.date: 01/30/2024
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: monaberdugo
ms.reviewer: Kay, Rui
author: mberdugo
---

# Use hot and cold table partitions to optimize very large Power BI data models

This article describes how to use hot and cold table partitions to optimize very large data models. Partitions provide a way to divide a table’s data into discrete subsets. Partitions are *not* directly exposed in the standard Power BI data modeling tools, but you can take advantage of advanced partitioning methods by configuring an incremental refresh policy in Power BI Desktop. Incremental refresh relies on partitions, as explained in [Incremental refresh and real-time data for datasets](/power-bi/connect-data/incremental-refresh-overview). This feature enables data model creators of any skill level to optimize data import without having to dive too deeply into table partitioning concepts.

## Prerequisites

Using hot and cold table partitions goes beyond what an incremental refresh policy can accomplish and assumes familiarity with typical table partitioning schemes and XMLA-based tools. Due to the relative complexity of this technique, it's most suitable for advanced users with experience in the following areas:

1. Understanding table partitioning concepts, how to import mode partitions, *DirectQuery* mode, and *Dual* mode work.

1. Knowledge of how to create hybrid tables using XMLA-based tools. Hybrid tables use one or more import-mode partitions and one *DirectQuery* partition.

1. Knowledge of the requirements of the DAX functions you can use to specify a `DataCoverageDefinition`. This is a new property for *DirectQuery* partitions to describe what data the *DirectQuery* partition of a hybrid table contains so that the Power BI engine can exclude this partition from query processing where appropriate. Excluding the *DirectQuery* partition can help to avoid unnecessary data source queries and improve the performance of DAX query processing.

1. Understanding the difference between regular and limited table relationships. For example, the RELATED function is useful if you want to define the data coverage of a facts table partition based on the values from a related date dimension table. Keep in mind that the facts table partition is a *DirectQuery* partition with a chance of a limited relationship to the date table over which the RELATED function can't fetch values. In this scenario, RELATED only works if the date dimension table is a dual table. The date table has to be in *DirectQuery* or *Dual* mode. It can't be pure import.  

Be aware that an incorrectly defined `DataCoverageDefinition` could lead to wrong results because Power BI might incorrectly exclude the *DirectQuery* partition from query processing. So, make sure you compare the results with and without the `DataCoverageDefinition` to ensure they add up.

## When to use hot and cold table partitions

Here's an example in which hot and cold partitions can help fine-tune a hybrid table for historic analysis. Assume you have a very large data source, accumulated over many years. The primary use is to analyze the most recent data from the last couple of years. Occasionally, you also want to analyze older data. Perhaps you noticed a recent sharp sales increase year over year. Did that ever happen before? Is it the highest sales spike since the beginning of sales tracking?  

Without support for hot and cold partitions, this kind of historic analysis would require you to import all the historic data along with the more recent data into the facts table. At best, this is an inefficient use of resources as the primary analysis doesn’t even use any of the older historic data. At worst, the data volume is so large that it can’t even be imported in full. You either have to switch the data model to *DirectQuery* mode and accept a performance penalty in comparison to import mode, or you can build separate models and force your users to switch between reports. A hybrid table with hot and cold partitions gives you a better option.

## How to use hot and cold table partitions

First, configure the sales table with a **hot** import mode partition for the most recent data and keep the older data in a **cold** *DirectQuery* partition, as the following diagram illustrates for the FactInternetSales table of an AdventureWorks sample data model. Any rows with an *OrderDateKey* greater than or equal to 20200101 are imported into the data model via the hot import-mode partition. Rows with an *OrderDateKey* less than 20200101 are covered through the cold *DirectQuery* partition. Now, Power BI can deliver the primary use cases quickly with import mode, and you don’t need to import vast volumes of historical data that you only analyze occasionally because the *DirectQuery* partition has this covered.

:::image type="content" source="./media/table-partitions/sample-data-model.png" alt-text="Screenshot of the Fact Internet Sales table of an Adventure Works sample data model. The fact internet dales table is opened with the filtered rows showing.":::

If you have an [AdventureWorks sample data warehouse](/sql/samples/adventureworks-install-configure) and want to follow along, here are the general steps:

1. **Create the dataset**. Use Power BI Desktop to create an AdventureWorks dataset and report. Include all the tables in pure *DirectQuery* mode. Then, convert all the tables except the `FactInternetSales` table to *Dual* mode. Leave the `FactInternetSales` table in *DirectQuery* mode.

1. **Upload the dataset**. Use a workspace hosted on Power BI Premium with the XMLA endpoint enabled for write operations.  

1. **Update the compatibility level**. Open the workspace with your AdventureWorks dataset in SQL Server Management Studio (SSMS). Right click the **AdventureWorks dataset** > **Script** > **Script Database as** **Create or Replace to**, and select **New query editor window**. Set the compatibilityLevel property to 1603 (or higher). Select **Execute** or press F5. Verify that the operation finishes successfully.

    :::image type="content" source="./media/table-partitions/compatibility-level.png" alt-text="Screenshot of script with compatibility level set to 1603.":::

1. **Configure the *FactInternetSales* table partitions**.  Right click the **AdventureWorks dataset** > **Script** > **Script Database as** **Create or Replace to**, and select **New query editor window**. Replace the entire partitions section with the following section. Make sure you update the Sql.Database lines to point to the *AdventureWorksDW* database in your environment. Select **Execute** or press F5. Verify that the operation finishes successfully.

    ```sql
       "partitions": [ 
        { 
          "name": "FactInternetSales-DQ-Partition", 
          "mode": "directQuery", 
          "dataView": "full", 
          "source": { 
            "type": "m", 
            "expression": [ 
              "let", 
              "    Source = Sql.Database(\"demo.database.windows.net\", \"AdventureWorksDW\"),", 
              "    dbo_FactInternetSales = Source{[Schema=\"dbo\",Item=\"FactInternetSales\"]}[Data],", 
              "    #\"Filtered Rows\" = Table.SelectRows(dbo_FactInternetSales, each [OrderDateKey] < 20200101)", 
              "in", 
              "    #\"Filtered Rows\"" 
            ] 
          } 
        }, 
        { 
          "name": "FactInternetSales-Import-Partition", 
          "mode": "import", 
          "source": { 
            "type": "m", 
            "expression": [ 
              "let", 
              "    Source = Sql.Database(\"demo.database.windows.net\", \"AdventureWorksDW\"),", 
              "    dbo_FactInternetSales = Source{[Schema=\"dbo\",Item=\"FactInternetSales\"]}[Data],", 
              "    #\"Filtered Rows\" = Table.SelectRows(dbo_FactInternetSales, each [OrderDateKey] >= 20200101)", 
              "in", 
              "    #\"Filtered Rows\"" 
            ] 
          } 
        } 
      ],    
    ```

1. **Process the data model**. In the Power BI portal, open the workspace with your *AdventureWorks* dataset and perform an on-demand refresh of the dataset to load the import partition with data.

1. **Verify that the reports show recent and historical data**. Open your *AdventureWorks* and verify that the report is able to show results for sales transactions before and after Jan 1, 2020, as in the following screenshot.

:::image type="content" source="./media/table-partitions/internet-sales-before-after.png" alt-text="Screenshot of two different reports. One shows data from 2020 and one shows data from 2019.":::

## Define the data coverage of the *DirectQuery* partition

The solution works seamlessly over recent and historical data. However, by default Power BI queries all table partitions, because it doesn't know what data each partition covers. Therefore, Power BI still queries the DirectQuery partition even for those years that the DirectQuery partition doesn't cover. The sales data is readily available in the import partition and the DirectQuery partition doesn't contribute any rows, but this superfluous source querying can still cause noticeable load on the data source and contribute delays to DAX query processing. To avoid this superfluous source querying, use the `DataCoverageDefinition`.

As the following screenshot shows, the Power BI report still sends several unnecessary SQL queries for 2020 to the data source as each visual’s DAX query causes Power BI to query the *DirectQuery* partition.

:::image type="content" source="./media/table-partitions/partition-queries.png" alt-text="Screenshot of DAX queries.":::

By setting the `dataCoverageDefinition` property on the *DirectQuery* partition as in the following TMSL snippet, these SQL queries are avoided. Keep in mind, however, that you must refresh the dataset after you apply or change a data coverage definition. A process recalc is enough to evaluate the data coverage definition. If you forget this step, queries that touch the partition fail with an error message stating "DataCoverageDefinition of the DQ partition in table '[Table Name]' is not yet calculated after a recent change. It needs to be reprocessed".  

```sql
        { 
          "name": "FactInternetSales-DQ-Partition", 
          "mode": "directQuery", 
          "dataView": "full", 
          "source": { 
            "type": "m", 
            "expression": [ 
              "let", 
              "    Source = Sql.Database(\"demopm.database.windows.net\", \"AdventureWorksDW2020\"),", 
              "    dbo_FactInternetSales = Source{[Schema=\"dbo\",Item=\"FactInternetSales\"]}[Data],", 
              "    #\"Filtered Rows\" = Table.SelectRows(dbo_FactInternetSales, each [OrderDateKey] < 20200101)", 
              "in", 
              "    #\"Filtered Rows\"" 
            ] 
          },  
"dataCoverageDefinition": {  
                  "description": "DQ partition with all sales from 2017, 2018, and 2019.",  
                  "expression": "RELATED('DimDate'[CalendarYear]) IN {2017,2018,2019}"  
                }  
        } 
```

As mentioned earlier, the `dataCoverageDefinition` property helps eliminate unnecessary data source load. It also improves the analysis performance for recent data because now Power BI can exclude the DirectQuery partition from DAX query processing where appropriate. You can define straightforward data coverage expressions for single values as well as ranges with simple AND, OR, and NOT operators. You can also use the RELATED function to define the data coverage based on a column from a dimension table that has a regular relationship to the fact table. If a data coverage expression uses columns from a dimension table, make sure the dimension table is in *dual* mode. You can also define the data coverage based on columns from the fact table itself. Refer to the following table for supported operations, categorized into three groups.  

|       Type                           |                                                           Comments                                                        |                                                                                                                                                                                                        Examples                                                                                                                                                                                                    |
|--------------------------------------|:-------------------------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|      Single predicate (value based)  |     Equality, inequality, and IN operators  <br> Support both dimension and fact tables                                       |     RELATED('Date'[Year]) = 2020 <br> NOT RELATED('Date'[Year]) = 2020 <br>  RELATED('Date'[Year]) IN {2020, 2021, 2022} <br>  InternetSales'[SalesAmt] = CURRENCY(100.0) <br>  NOT InternetSales'[SalesAmt] = CURRENCY(100.0) <br>  InternetSales'[SalesAmt] IN {CURRENCY(100.0), CURRENCY(200.0)}                                                                                                                                   |
|      Single predicate (range based)  |     Can be comparison operators like >, <, >=, <= <br> Require the dimension table to be in Dual mode                         |     RELATED('Date'[Year]) > 2020 <br>  RELATED('Date'[Year]) <= 2020                                                                                                                                                                                                                                                                                                                                                   |
|      Multiple predicates             |     Equality, inequality, and comparison <br> Does not support IN operator <br> Limited to a single dimension table in dual mode  |     RELATED('Date'[Year]) > 2010 && RELATED('Date'[Year]) > 2020  <br> RELATED('Date'[Year]) = 2020 && RELATED('Date'[Calendar Quarter]) = 1  <br> RELATED('Date'[Year]) > 2020 && NOT RELATED('Date'[Calendar Quarter]) = 1  <br> RELATED('Date'[Year]) > 2020 && RELATED('Date'[Calendar Quarter]) < 3 <br>  RELATED('Date'[Year]) > 2020 && (RELATED('Date'[Calendar Quarter]) = 1 \|\| RELATED('Date'[Calendar Quarter]) = 2)  |

The `DataCoverageDefinition` property on *DirectQuery* partitions enables you to optimize even the largest Power BI data models based on hot partitions in import mode and cold partitions in *DirectQuery* mode by avoiding unnecessary querying of the data source.
This source query reduction helps to boost report performance when analyzing hot data. It also helps to decrease the load on the data source, and in this way helps to maximize the scale of your data source. Optimizing a data model by using the `dataCoverageDefinition` property is still an advanced scenario.

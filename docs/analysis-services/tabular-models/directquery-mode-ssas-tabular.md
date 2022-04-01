---
title: "DirectQuery mode in Analysis Services | Microsoft Docs"
description: Describes DirectQuery mode for tabular models.
ms.date: 08/27/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# DirectQuery mode in tabular models

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

This article describes *DirectQuery mode* for Analysis Services tabular models at the 1200 and higher compatibility levels. DirectQuery mode can be enabled for models you're designing in Visual Studio, or for tabular models that have already been deployed, you can change to DirectQuery mode by using SQL Server Management Studio (SSMS). Before choosing DirectQuery mode, it's important to understand both the benefits and limitations.
  
## Benefits

By default, tabular models use an in-memory cache to store and query data. When tabular models query data residing in-memory, even complex queries can be very fast. However, there are some limitations to using cached data, for example, very large data sets can exceed available memory and processing (refresh) of in-memory model data can require excessive amounts of available resources if needed frequently.
  
DirectQuery overcomes these limitations while also leveraging RDBMS features making query execution more efficient. With DirectQuery:  
  
- Data is up-to-date. Because data is always queried at the data source, client reporting applications are always getting the latest data.

- There is no extra management overhead of having to maintain a separate copy of the data (in the in-memory cache). No processing (refresh) of model data is required. Changes to the underlying source data can be immediately reflected in queries against the data model.  
  
- Datasets can be larger than the memory capacity of an Analysis Services server resource.  
  
- DirectQuery can take advantage of provider-side query acceleration, such as that provided by memory-optimized column indexes.  
  
- Security can be enforced by the back-end source database by using row-level security features from the database (alternatively, you can use row-level security rules defined in the model by using DAX).  
  
- If the model contains complex formulas that might require multiple queries, Analysis Services can perform optimization to ensure that the query plan for the query executed against the back-end database will be as efficient as possible.  

## Limitations

Tabular models in DirectQuery mode have some limitations. Before switching modes, it's important to determine whether the advantages of query execution on the backend server outweigh any reduction in functionality. If you change the mode of an existing model in Visual Studio, Tabular model designer will notify you of any features in your model that are incompatible with DirectQuery mode. Keep the following limitations in mind:  
  
|Feature|Restriction|  
|-|-|
|Data sources|DirectQuery models can only use data from a single relational database of the following types: Azure SQL Database, Azure Synapse Analytics, SQL Server,  Oracle, and Teradata.|
|SQL stored procedures|For DirectQuery models, stored procedures cannot be specified in a SQL statement to define tables. |
|Calculated tables|Calculated tables are not supported in DirectQuery models, but calculated columns are. If you try to convert a tabular model that contains a calculated table, an error will occur stating that the model cannot contain pasted data.|  
|Query limits|Default row limit is one million rows. This limit can be increases by specifying **MaxIntermediateRowSize**. To learn more, see [DAX Properties](../../analysis-services/server-properties/dax-properties.md).
|DAX formulas|When querying a tabular model in DirectQuery mode, Analysis Services converts DAX formulas and measure definitions into SQL statements. DAX formulas containing elements that cannot be converted into SQL syntax will return validation errors on the model.<br /><br /> This restriction is mostly limited to certain DAX table functions. For measures, DAX formulas are converted to set-based operations against the relational data store. This means that all measures created implicitly are supported. <br /><br /> When a validation error occurs, you'll need to re-write the formula, substituting a different function, or workaround it by using derived columns in the data source.  If a tabular model includes formulas containing incompatible functions, it will be reported when you switch to DirectQuery mode in the designer. <br /><br />Note: Some formulas in the model might validate when you switch the model to DirectQuery mode, but return different results when executed against the cache vs. the relational data store. This is because calculations against the cache use the semantics of the in-memory analytics engine, which contains features meant to emulate the behavior of Excel, whereas queries against data stored in the relational data source use the semantics of SQL.<br /><br />|  
|Formula consistency|In certain cases, the same formula can return different results in a cached model compared to a DirectQuery model that uses only the relational data store. These differences are a consequence of the semantic differences between the in-memory analytics engine and the data source.<br /><br />|  
|MDX limitations|No relative object names. All object names must be fully qualified.<br /><br /> No session-scope MDX statements (named sets, calculated members, calculated cells, visual totals, default members, and so forth), but you can use query-scope constructs, such as the 'WITH' clause.<br /><br /> No tuples with members from different levels in MDX subselect clauses.<br /><br /> No user-defined hierarchies.<br /><br /> No native SQL queries (normally, Analysis Services supports a T-SQL subset, but not for DirectQuery models).|  

## Connecting to a data source

When designing a DirectQuery model in Visual Studio, connecting to a data source and selecting the tables and fields to include in your model is much the same as with in-memory models.

If you've already turned on DirectQuery but haven't yet connected to a data source, you can use Get Data (or Data Import Wizard for legacy provider data sources) to connect to a data source, select tables and fields, and so on. The difference will be when you finish, no data is actually imported to the in-memory cache.

![DirectQuery import success](../../analysis-services/tabular-models/media/directquery-import-success.png)

If you've already used Get Data to import data, but haven't yet turned on DirectQuery mode, when you do, the in-memory cache will be cleared.

## Adding sample data to a DirectQuery model project

By default, when using Tabular model designer in Visual Studio (SSDT) to design a DirectQuery tabular model project, the model's workspace database doesn't contain any data. There is one default partition for each table and this partition directs all queries to the data source. Since DirectQuery was first introduced, Tabular model designer includes a **Set as Sample** feature in Partition Manager. This feature allows adding a copy partition to tables that can be used to import a small amount of sample data into the workspace database. This feature is meant help validate modeling decisions without impacting the data source.

> [!IMPORTANT]
> Currently, the **Set as Sample** feature *in Tabular model designer* is not supported. Disregard  **Table \<TableName> does not contain a sample partition; to use data in SSDT please add a sample partition** warnings.

## Deploying DirectQuery models

DirectQuery models are deployed the same as import models. However, unlike import models, if a DirectQuery model contains calculated items such as calculated columns or calculation groups, after being deployed you must perform a **Process Recalc** on all tables. To learn more, see [Process database, table, or partition](process-database-table-or-partition-analysis-services.md).

## See also

[Enable DirectQuery mode in Visual Studio](../../analysis-services/tabular-models/enable-directquery-mode-in-ssdt.md)  
[Enable DirectQuery mode in SSMS](../../analysis-services/tabular-models/enable-directquery-mode-in-ssms.md)  
[Define partitions in DirectQuery models](../../analysis-services/tabular-models/define-partitions-in-directquery-models-ssas-tabular.md)  [Test a model in DirectQuery mode](../../analysis-services/tabular-models/test-a-model-in-directquery-mode.md)  
[Data sources supported in Azure Analysis Services](/azure/analysis-services/analysis-services-datasource)  
[Data sources supported in SQL Server Analysis Services tabular 1400 and higher models](data-sources-supported-ssas-tabular-1400.md).
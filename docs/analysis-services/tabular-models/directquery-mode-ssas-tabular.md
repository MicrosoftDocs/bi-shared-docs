---
title: "DirectQuery mode in Analysis Services | Microsoft Docs"
ms.date: 01/29/2020
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

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

  This article describes *DirectQuery mode* for Analysis Services tabular models at the 1200 and higher compatibility levels
  . DirectQuery mode can be turned on for models you're designing in Visual Studio, or for tabular models that have already been deployed, you can change to DirectQuery mode in SSMS. Before choosing DirectQuery mode, it's important to understand both the benefits and restrictions.
  
##  <a name="bkmk_Benefits"></a> Benefits

 By default, tabular models use an in-memory cache to store and query data. When tabular models query data residing in-memory, even complex queries can be incredibly fast. However, there are some limitations to using cached data. Namely, large data sets can exceed available memory, and data freshness requirements can be difficult if not impossible to achieve on a regular processing schedule.  
  
 DirectQuery overcomes these limitations while also leveraging RDBMS features making query execution more efficient. With DirectQuery:  
  
-   Data is up-to-date, and there is no extra management overhead of having to maintain a separate copy of the data (in the in-memory cache). Changes to the underlying source data can be immediately reflected in queries against the data model.  
  
-   Datasets can be larger than the memory capacity of an Analysis Services server.  
  
-   DirectQuery can take advantage of provider-side query acceleration, such as that provided by memory optimized column indexes.  
  
-   Security can be enforced by the back-end database , using row-level security features from the database (alternatively, you can use row-level security in the model via DAX).  
  
-   If the model contains complex formulas that might require multiple queries, Analysis Services can perform optimization to ensure that the query plan for the query executed against the back-end database will be as efficient as possible.  
  
##  <a name="bkmk_prereq"></a>Restrictions

Tabular models in DirectQuery mode have some restrictions. Before switching modes, it's important to determine whether the advantages of query execution on the backend server outweigh any reduction in functionality.  
  
 If you change the mode of an existing model in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], the model designer will notify you of any features in your model that are incompatible with DirectQuery mode.  
  
 The following list summarizes the main feature restrictions to keep in mind:  
  
|||  
|-|-|  
|**Feature area**|**Restriction**|  
|**Data sources**|DirectQuery models can only use data from a single relational database of the following types: SQL Server, Azure SQL Database, Oracle, and Teradata.  See Data sources supported for DirectQuery later in this article for version and provider information.| 
|**SQL stored procedures**|For DirectQuery models, stored procedures cannot be specified in a SQL statement to define tables when using Data Import Wizard. |   
|**Calculated tables**|Calculated tables are not supported in DirectQuery models, but calculated columns are. If you try to convert a tabular model that contains a calculated table, an error will occur stating that the model cannot contain pasted data.|  
|**Query limits**|Default row limit is one million rows, which you can increase by specifying **MaxIntermediateRowSize** in the msmdsrv.ini file. See [DAX Properties](../../analysis-services/server-properties/dax-properties.md) for details.
|**DAX formulas**|When querying a tabular model in DirectQuery mode, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] converts DAX formulas and measure definitions into SQL statements. DAX formulas containing elements that cannot be converted into SQL syntax will return validation errors on the model.<br /><br /> This restriction is mostly limited to certain DAX functions. For measures, DAX formulas are converted to set-based operations against the relational data store. This means that all measures created implicitly are supported. <br /><br /> When a validation error occurs, you'll need to re-write the formula, substituting a different function, or workaround it by using derived columns in the data source.  If a tabular model includes formulas containing incompatible functions will be reported when you switch to DirectQuery mode in the designer. <br /><br />**Note:**  Some formulas in the model might validate when you switch the model to DirectQuery mode, but return different results when executed against the cache vs. the relational data store. This is because calculations against the cache use the semantics of the in-memory analytics (engine, which contains features meant to emulate the behavior of Excel, whereas queries against data stored in the relational data source use the semantics of SQL Server.<br /><br />To learn more, see [DAX formula compatibility in DirectQuery mode](../../analysis-services/tabular-models/dax-formula-compatibility-in-directquery-mode-ssas-2016.md).|  
|**Formula consistency**|In certain cases, the same formula can return different results in a cached model compared to a DirectQuery model that uses only the relational data store. These differences are a consequence of the semantic differences between the in-memory analytics engine and SQL Server.<br /><br /> For a complete list of compatibility issues, including functions that might return different results when the model is deployed to real-time, see [DAX formula compatibility in DirectQuery mode (SQL Server Analysis Services)](../../analysis-services/tabular-models/dax-formula-compatibility-in-directquery-mode-ssas-2016.md).|  
|**MDX limitations**|No relative object names. All object names must be fully qualified.<br /><br /> No session-scope MDX statements (named sets, calculated members, calculated cells, visual totals, default members, and so forth), but you can use query-scope constructs, such as the 'WITH' clause.<br /><br /> No tuples with members from different levels in MDX subselect clauses.<br /><br /> No user-defined hierarchies.<br /><br /> No native SQL queries (normally, Analysis Services supports a T-SQL subset, but not for DirectQuery models).|  

## Data sources supported for DirectQuery

See [Data sources supported in SQL Server Analysis Services tabular 1400 models](data-sources-supported-ssas-tabular-1400.md)

## Connecting to a data source

When designing a DirectQuery model in Visual Studio, connecting to a data source and selecting the tables and fields to include in your model is much the same as with in-memory models. 

If you've already turned on DirectQuery but haven't yet connected to a data source, you can use the Table Import Wizard to connect to your data source, select tables and fields, specify a SQL query, and so on. The difference will be when you finish, no data is actually imported to the in-memory cache. 

![DirectQuery import success](../../analysis-services/tabular-models/media/directquery-import-success.png)

If you've already used Table Import Wizard to import data, but haven't yet turned on DirectQuery mode, when you do, the in-memory cache will be cleared.

## Deploying DirectQuery models

DirectQuery models are deployed the same as import models. However, unlike import models, if a DirectQuery model contains calculated items, calculated columns, calculated tables, after being deployed you must perform a **Process Recalc** on the database. To learn more about processing a model database from SSMS, see [Process Database, Table, or Partition](process-database-table-or-partition-analysis-services.md).

  
## Additional articles in this section

[Enable DirectQuery mode in Visual Studio](../../analysis-services/tabular-models/enable-directquery-mode-in-ssdt.md)

[Enable DirectQuery mode in SSMS](../../analysis-services/tabular-models/enable-directquery-mode-in-ssms.md)

[Add sample data to a DirectQuery model in Design Mode](../../analysis-services/tabular-models/add-sample-data-to-a-directquery-model-in-design-mode.md)

[Define partitions in DirectQuery models](../../analysis-services/tabular-models/define-partitions-in-directquery-models-ssas-tabular.md)
  
[Test a model in DirectQuery mode](../../analysis-services/tabular-models/test-a-model-in-directquery-mode.md)

[DAX formula compatibility in DirectQuery mode](../../analysis-services/tabular-models/dax-formula-compatibility-in-directquery-mode-ssas-2016.md)
  

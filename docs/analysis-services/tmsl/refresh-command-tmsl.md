---
title: "Refresh command (TMSL) | Microsoft Docs"
description: Learn about the Refresh command, which processes objects in the current database and always runs in parallel, unless you throttle it.
ms.date: 06/22/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: tmsl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
---
# Refresh command (TMSL)

[!INCLUDE[ssas-appliesto-sql2016-later-aas-pbip](../includes/ssas-appliesto-sql2016-later-aas-pbip.md)]

  Processes objects in the current database.   
**Refresh** always runs in parallel unless you throttle it with [Sequence command &#40;TMSL&#41;](sequence-command-tmsl.md).  
  
 You can override some properties of some objects during a data refresh operation:  
  
- Change the **QueryDefinition** property of a **Partition** object to import data using an on-the-fly filter expression.  
  
- Provide data source credentials as part of a **Refresh** command,  in the **ConnectionString** property of a **DataSource**  object. This  approach could be considered more secure, as credentials are provided and used temporarily for the duration of the operation, rather than stored.  
::: moniker range="asallproducts-allversions || power-bi-premium-current"
- Override default Power BI dataset incremental refresh policy.   
::: moniker-end

 See the examples in this topic for an illustration of these property overrides.  
  
> [!NOTE]  
>  Unlike multidimensional processing, there is no special handling of processing errors for tabular processing.  

## Request  

 **Refresh** takes a type parameter and object definition.  
  
```json
    {  
        "refresh": {  
            "description": "Parameters of Refresh command of Analysis Services JSON API",  
            "properties": {  
            "type": {  
                "enum": [  
                "full",  
                "clearValues",  
                "calculate",  
                "dataOnly",  
                "automatic",  
                "add",  
                "defragment"  
                ]  
            },  
            "objects": [  
```  
  
 The **type** parameter  sets a scope on the processing operation.  
  
| Refresh type | Applies to | Description |
| ------------ | ---------- | ----------- |
|full|Database,<br />Table,<br />Partition|For all partitions in the specified partition, table, or database, refresh data and recalculate all dependents. For a calculation partition, recalculate the partition and all its dependents.|  
|clearValues|Database,<br />Table,<br />Partition|Clear values in this object and all its dependents.|  
|calculate|Database,<br />Table,<br />Partition|Recalculate this object and all its dependents, but only if needed. This value does not force recalculation, except for volatile formulas.|  
|dataOnly|Database,<br />Table,<br />Partition|Refresh data in this object and clear all dependents.|  
|automatic|Database,<br />Table,<br />Partition|If the object needs to be refreshed and recalculated, refresh and recalculate the object and all its dependents. Applies if the partition is in a state other than Ready.|  
|add|Partition|Append data to this partition and recalculate all dependents. This command is valid only for regular partitions and not for calculation partitions.|  
|defragment|Database,<br />Table|Defragment the data in the specified table. As data is added to or removed from a table, the dictionaries of each column can become polluted with values that no longer exist in the actual column values. The defragment option will clean up the values in the dictionaries that are no longer used.|  
  
 You can refresh the following objects:  
  
 [Database object &#40;TMSL&#41;](database-object-tmsl.md) Process a database.  
  
```json
{  
  "refresh": {  
    "type": "automatic",  
    "objects": [  
      {  
        "database": "AdventureWorksTabular1200"  
      }  
    ]  
  }  
}  
```  
  
 [Tables object &#40;TMSL&#41;](tables-object-tmsl.md) Process a single table.  
  
```json
{  
  "refresh": {  
    "type": "automatic",  
    "objects": [  
      {  
        "database": "AdventureWorksTabular1200",  
        "table": "Date"  
      }  
    ]  
  }  
}  
```  
  
 [Partitions object &#40;TMSL&#41;](partitions-object-tmsl.md) Process a single partition within a table.  
  
```json
{  
  "refresh": {  
    "type": "automatic",  
    "objects": [  
      {  
        "database": "AdventureWorksTabular1200",  
        "table": "FactSalesQuota",  
        "partition": "FactSalesQuota"  
      },  
      {  
        "database": "AdventureWorksTabular1200",  
        "table": "FactSalesQuota",  
        "partition": "FactSalesQuota - 2011"  
      }  
    ]  
  }  
}  
```

::: moniker range="asallproducts-allversions || power-bi-premium-current"
### Optional parameters

For Power BI datasets, the following parameters can be added to a TMSL refresh command to override the default incremental refresh behavior:

- **applyRefreshPolicy** – If a table has an incremental refresh policy defined, applyRefreshPolicy will determine if the policy is applied or not. If the policy is not applied, a process full operation will leave partition definitions unchanged and all partitions in the table will be fully refreshed. Default value is true.

- **effectiveDate** – If an incremental refresh policy is being applied, it needs to know the current date to determine rolling window ranges for the historical range and the incremental range. The effectiveDate parameter allows you to override the current date. This is useful for testing, demos, and business scenarios where data is incrementally refreshed up to a date in the past or the future (for example, budgets in the future). The default value is the current date.

```json
{
  "refresh": {
    "type": "full",

    "applyRefreshPolicy": true,
    "effectiveDate": "12/31/2013",

    "objects": [
      {
        "database": "IR_AdventureWorks", 
        "table": "FactInternetSales" 
      }
    ]
  }
}
```

The following table shows the impact when **applyRefreshPolicy** is true (default) on each of the refresh types for a table that contains an incremental refresh policy:

|Refresh type  |Impact  |
|---------|---------|
|full     |  The policy is applied as described in [Incremental refresh in Power BI](https://docs.microsoft.com/power-bi/admin/service-premium-incremental-refresh). Assuming historical partitions have already been created by a prior refresh operation, a summary is described here: </br>- New partitions are added to the incremental range if needed. </br>- If no pollingExpression is defined for detection of data changes, all partitions in the incremental range are refreshed in full. </br>- If a pollingExpression is defined, it is evaluated for each partition in the incremental range. Only those that return a different polling result compared to the previous refresh operation are refreshed in full. </br>- Historical partitions are not refreshed regardless of whether they have been cleared of data. </br>- Historical partitions that fall out of range are deleted. </br>- Recalculation of affected partitions and dependents.|
|clearValues     |   applyRefreshPolicy does not affect behavior.      |
|calculate     |   applyRefreshPolicy does not affect behavior.      |
|dataOnly    |    Same as type=full, but without recalculation of affected partitions and dependents.     |
|automatic     |  Same as type=full, but partitions in the incremental range are refreshed using type=automatic.       |
|add     |   applyRefreshPolicy does not affect behavior.      |
|defragment     |   applyRefreshPolicy does not affect behavior.      |

::: moniker-end

## Response  

 Returns an empty result when the command succeeds. Otherwise, an XMLA exception is returned.  
  
## Examples  

 Override both the **ConnectionString** and **QueryDefinition** of a partition.  
  
```json   
{
  "refresh": {
    "type": "dataOnly",
    "objects": [
      {
        "database": "AdventureWorksDW2017",
        "table": "DimCustomer"
      }
    ],
    "overrides": [
      {
        "dataSources": [ // Bindings for DataSources​
          {
            "originalObject": {
              "database": "AdventureWorksDW2017",
              "dataSource": "SqlServer localhost"
            },
            "connectionString": "Provider=SQLNCLI11.1;Data Source=.;Persist Security Info=True;User ID=YourSQLLogin;Password=YourPassword;Initial Catalog=AdventureWorksDW2017"
          }
        ],
        "partitions": [ // Bindings for Partitions​
          {
            "originalObject": {
              "database": "AdventureWorksDW2017",
              "table": "DimCustomer",
              "partition": "DimCustomer"
            },
            "source": {
              "query": "SELECT * FROM [dbo].[DimCustomer]"
            }
          }
        ]
      }
    ]
  }
}
```  
  
 Scope particular overrides by setting the type parameter to a **dataOnly** refresh, metadata stays intact.  
  
```json   
{
  "refresh": {
    "type": "dataOnly",
    "objects": [
      {
        "database": "TMTestDB",
        "table": "Customer"
      },
      {
        "database": "TMTestDB",
        "table": "Sales"
      }
    ],
    "overrides": [
      {
        "scope": {
          "database": "TMTestDB",
          "table": "Sales"
        },
        "dataSources": [
          {
            "originalObject": {
              "dataSource": "SqlServer sqlcldb2 AS_foodmart_2000"
            },
            "connectionString": "Provider=SQLNCLI11;Data Source=sqlcldb2;Initial Catalog=AS_foodmart_2000;Integrated Security=SSPI;Persist Security Info=false"
          }
        ]
      }
    ]
  }
}
```  
  
## Usage (endpoints)  

 This command element is used in a statement of the Execute Method (XMLA) call over an XMLA endpoint, exposed in the following ways:  
  
- As an XMLA window in SQL Server Management Studio (SSMS)  
  
- As an input file to the **invoke-ascmd** PowerShell cmdlet  
  
- As an input to an SSIS task or SQL Server Agent job  
  
 You can generate a ready-made script  for this command from SSMS. For example, you can click the **Script** in a Processing dialog box.

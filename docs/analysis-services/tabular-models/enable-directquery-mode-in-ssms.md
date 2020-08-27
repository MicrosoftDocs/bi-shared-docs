---
title: "Enable Analysis Services DirectQuery mode in SSMS | Microsoft Docs"
description: Describes how to enable DirectQuery mode for tabular models by using SQL Server Management Studio.
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
# Enable DirectQuery mode in SSMS

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

You can  change the data access properties of a tabular model that has already been deployed, enabling DirectQuery mode, where queries execute against a backend relational data source rather than cached data residing in-memory.  
  
> [!IMPORTANT]  
> It's recommended you use Tabular model designer in Visual Studio instead of SQL Server Management Studio (SSMS) to switch data storage modes. When using SSMS to change the model mode, and then follow that up with deployment to the server,  the model and database stay in sync. Moreover, changing the storage modes in the model lets you review any validation errors that occur. When using SSMS as described in this article, validation errors are not reported.  
  
## Requirements  

 Enabling the use of DirectQuery mode on a tabular model is a multi-step process:  
  
- Ensure the model does not have features which might cause validation errors in DirectQuery mode, and then change the data storage mode on the model from in-memory to DirectQuery.  
  
     A list of feature limitations is documented in [DirectQuery mode](../../analysis-services/tabular-models/directquery-mode-ssas-tabular.md).  
  
- Review the connection string and credentials used by the deployed database to retrieve data from the backend external database. Make sure there is only one connection, and that its settings are suitable for query execution.  
  
     Tabular databases that weren't specifically designed for DirectQuery could have multiple connections which now need to be reduced to one, as required for DirectQuery mode.  
  
     Credentials originally used for processing data will now be used  to query data. As part of DirectQuery configuration, review and possibly change the account if you use different ones for dedicated operations.  
  
     DirectQuery mode is the only scenario in which Analysis Services does trusted delegation. If your solution calls for delegation to get user-specific query results, the account used to connect to the backend database must be allowed to delegate the identity of the user making the request, and user identities must have Read permissions on the backend database.  
  
- As a last step, confirm that DirectQuery mode is operational through query execution.  

## Switch to DirectQuery mode 
  
1. In Object Explorer, right-click the database > **Properties** > **Model** > **Default Mode**.  
  
2. Set the mode to **DirectQuery**.  
  
    |**Valid values**|**Description**|  
    |-|-|  
    |**DirectQuery**|Queries are executed against a backend relational database, using the data source connection defined for the model.<br /><br /> Queries to the model are converted to native database queries and redirected to the data source.<br /><br /> When you process a model set to DirectQuery mode, only metadata is compiled and deployed. The data itself is external to the model, residing in the database files of the operative data source.|  
    |**Import**|Queries are executed against the tabular database in either MDX or DAX.<br /><br /> When you process a model set to Import mode,  data is retrieved from a backend data source and stored on disk. When the database is loaded, data is copied entirely into memory for very fast table scans and queries.<br /><br /> This is the default mode for tabular models, and it is the only mode for certain (non-relational) data sources.|  
    | **Dual** | Allows both Import and DirectQuery. This mode is not supported in Azure Analysis Services or Power BI Premium. |

## Check connection properties  

 Depending on how the data source connection is set up, switching to DirectQuery could change the security context of the connection. When changing the data access mode, review impersonation and connection string properties to verify the login is valid for ongoing connections to the backend database.  
  
 Review the **Configure Analysis Services for trusted delegation** section in [Configure Analysis Services for Kerberos constrained delegation](../../analysis-services/instances/configure-analysis-services-for-kerberos-constrained-delegation.md) for background information on delegation of a user identity for DirectQuery scenarios.  
  
1. In Object Explorer, expand **Connections** and double-click a connection to view its properties.  
  
     For DirectQuery models, there should only be one connection defined for the database, and the data source must be relational, and of a supported database type. See [Data Sources Supported](../../analysis-services/tabular-models/data-sources-supported-ssas-tabular.md).  
  
2. **Connection string** should specify the server, database name, and the authentication method used in DirectQuery operations. If you're using SQL Server authentication, you can specify the database login here.  
  
3. **Impersonation Info** is used for Windows authentication. Options that are valid for tabular models in DirectQuery mode include the following:  
  
    - **Use the service account**. You can choose this option if the Analysis Services service account has read permissions on the relational database.  
  
    - **Use a specific user name and password**. Specify a Windows user account that has read permissions on the relational database.  
  
 Note that these credentials are used only for answering queries against the relational data store; they are not the same as the credentials used for processing the cache of a hybrid model.  
  
 Impersonation cannot be used when the model is used within memory only. The setting **ImpersonateCurrentUser**, is invalid unless the model is using DirectQuery mode.  
  
## Validate DirectQuery access  
  
1. Start a trace using either SQL Server Profiler or xEvents in Management Studio, connected to the relational database on SQL Server.  
  
     If you are using Oracle or Teradata, use the tracing tools for those database platforms.  
  
2. In Management Studio, enter and then execute a simple MDX query, such as `select <some measure> on 0 from model.`.  
  
3. In the trace, you should see evidence of query execution on the relational database.  
  
## See also  

 [Compatibility level](../../analysis-services/tabular-models/compatibility-level-for-tabular-models-in-analysis-services.md)   
 [Data sources supported](../../analysis-services/tabular-models/data-sources-supported-ssas-tabular.md)   
 [Extended events](/sql/relational-databases/extended-events/extended-events)   

  
  

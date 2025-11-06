---
title: "Dynamic Management Views (DMVs) in Analysis Services | Microsoft Docs"
description: Learn about Dynamic Management Views in SQL Server Analysis Services that return information about model objects, server operations, and server health.
ms.date: 12/29/2020
ms.service: analysis-services
ms.custom:
ms.topic: conceptual
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Dynamic Management Views (DMVs)

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

Analysis Services Dynamic Management Views (DMVs) are queries that return information about model objects, server operations, and server health. The query, based on SQL, is an interface to *schema rowsets*. Schema rowsets are predescribed tables that contain information about Analysis Services objects and server state, including database schema, active sessions, connections, commands, and jobs that are executing on the server.

For **Power BI Premium semantic models**, DMVs for querying through the XMLA endpoint are limited to those that require database admin permissions. Some DMVs are not supported because they require Analysis Services server admin permissions.

DMV queries are an alternative to running XML/A Discover commands. For most administrators, writing a DMV query is simpler because the syntax is based on SQL. In addition, the result is returned in a table format that is easier to read and copy. 
  
Most DMV queries use a **SELECT** statement and the **$System** schema with an XML/A schema rowset, for example:  
  
```sql
SELECT * FROM $System.<schemaRowset>  
```  
  
 DMV queries return information about server and object state at the time the query is run. To monitor operations in real-time, use tracing instead. To learn more about real-time monitoring using traces, see [Use SQL Server Profiler to Monitor Analysis Services](../../analysis-services/instances/use-sql-server-profiler-to-monitor-analysis-services.md).  
  
## Query syntax

The query engine for DMVs is the Data Mining parser. The DMV query syntax is based on the SELECT &#40;DMX&#41; statement. Although DMV query syntax is based on a SQL SELECT statement, it does not support the full syntax of a SELECT statement. Notably, JOIN, GROUP BY, LIKE, CAST, and CONVERT are not supported.  
  
```sql
SELECT [DISTINCT] [TOP <n>] <select list>  
FROM $System.<schemaRowset>  
[WHERE <condition expression>]  
[ORDER BY <expression>[DESC|ASC]]  
```  
  
The following example for DISCOVER_CALC_DEPENDENCY illustrates the use of the WHERE clause for supplying a parameter to the query:  
  
```sql
SELECT * FROM $System.DISCOVER_CALC_DEPENDENCY  
WHERE OBJECT_TYPE = 'ACTIVE_RELATIONSHIP'  
```  
  
For schema rowsets that have restrictions, the query must include the SYSTEMRESTRICTSCHEMA function. The following example returns CSDL metadata about 1103 compatibility level tabular models. Note that CATALOG_NAME is case-sensitive:  
  
```sql
Select * from SYSTEMRESTRICTSCHEMA ($System.Discover_csdl_metadata, [CATALOG_NAME] = 'Adventure Works DW')  
```  

## Examples and scenarios

A DMV query can help you answer questions about active sessions and connections, and which objects are consuming the most CPU or memory at a specific point in time. For example:
  
 `Select * from $System.discover_object_activity`  
This query reports on object activity since the service last started. 
  
 `Select * from $System.discover_object_memory_usage`  
This query reports on memory consumption by object.  
  
 `Select * from $System.discover_sessions`  
This query reports on active sessions, including session user and duration.  
  
 `Select * from $System.discover_locks`   
This query returns a snapshot of the locks used at a specific point in time.  

## Tools and permissions

You can use any client application that supports MDX or DMX queries. In most cases, it's best to use SQL Server Management Studio. You must have server administrator permissions on the instance to query a DMV.  
  
### To run a DMV query from SQL Server Management Studio

1. Connect to the server and model object you want to query. 
2. Right-click the server or database object > **New Query** > **MDX**.
3. Type your query, and then click **Execute**, or press F5.
  
## Schema rowsets

Not all schema rowsets have a DMV interface. To return a list of all the schema rowsets that can be queried using DMV, run the following query.  

```sql
SELECT * FROM $System.DBSchema_Tables   
WHERE TABLE_TYPE = 'SCHEMA'   
ORDER BY TABLE_NAME ASC  
```  
  
If a DMV is not available for a given rowset, the server returns error: `The <schemarowset> request type was not recognized by the server.` All other errors indicate problems with the syntax.  

Schema rowsets are described in two SQL Server Analysis Services protocols:

[[MS-SSAS-T]: SQL Server Analysis Services Tabular Protocol](/openspecs/sql_server_protocols/ms-ssas-t/) - Describes schema rowsets for tabular models at the 1200 and higher compatibility levels.

[[MS-SSAS]: SQL Server Analysis Services Protocol](/openspecs/sql_server_protocols/ms-ssas/) - Describes schema rowsets for multidimensional models and tabular models at the 1100 and 1103 compatibility levels.

### Rowsets described in the [MS-SSAS-T]: SQL Server Analysis Services Tabular Protocol

Note: This list may be incomplete. Refer to the [MS-SSAS-T] and [MS-SSAS] protocols for the latest.

|Rowset  |Description  |
|---------|---------|
|[TMSCHEMA_ANNOTATIONS](/openspecs/sql_server_protocols/ms-ssas-t/c52fc0b6-3be2-4e17-ad60-c5f9e1cfbc19)|Provides information about the Annotation objects in the model.|
|[TMSCHEMA_ATTRIBUTE_HIERARCHIES](/openspecs/sql_server_protocols/ms-ssas-t/c12d12a6-c648-4ff5-b69c-b3d68eaf57b8)     |   Provides information about the AttributeHierarchy objects for a column.      |
|[TMSCHEMA_CALCULATION_ITEMS](/openspecs/sql_server_protocols/ms-ssas-t/e5f9af60-a748-4f93-91e5-7635b2e25811)|Provides information about the CalculationItem objects in the tabular model.|
|[TMSCHEMA_CALCULATION_GROUPS](/openspecs/sql_server_protocols/ms-ssas-t/d2263ab0-01cc-46a2-9e0d-3ef6565cd0eb)|Provides information about the CalculationGroup objects in the tabular model.|
|[TMSCHEMA_COLUMNS](/openspecs/sql_server_protocols/ms-ssas-t/c6fdd3e5-47f0-41f6-89ca-0336465c631d)    |  Provides information about the Column objects in each table.       |
|[TMSCHEMA_COLUMN_PERMISSIONS](/openspecs/sql_server_protocols/ms-ssas-t/3987ef2f-8ef1-4934-94f6-97ade16de707)|Provides information about the ColumnPermission objects in each table-permission.|
|[TMSCHEMA_CULTURES](/openspecs/sql_server_protocols/ms-ssas-t/4faa5bb7-1975-4ae3-9bc2-3b8f4dffd507)|Provides information about the Culture objects in the model.|
|[TMSCHEMA_DATA_SOURCES](/openspecs/sql_server_protocols/ms-ssas-t/875f24a8-666b-420e-b23c-966bd3085fa0)   |   Provides information about the DataSource objects in the model.      |
|[TMSCHEMA_DETAIL_ROWS_DEFINITIONS](/openspecs/sql_server_protocols/ms-ssas-t/db8db782-29ae-4c85-844e-d3901af93fcb)|Provides information about the DetailRowsDefinition objects in the model.|
|[TMSCHEMA_EXPRESSIONS](/openspecs/sql_server_protocols/ms-ssas-t/ca94b8c6-b63b-432f-b79d-d2f776a71873)|Provides information about the Expression objects in the model.|
|[TMSCHEMA_FORMAT_STRING_DEFINITIONS](/openspecs/sql_server_protocols/ms-ssas-t/7bd68a16-5cc6-4704-ae11-1694598f1911)|Provides information about the FormatStringDefinition objects in the tabular model.|
|[TMSCHEMA_EXTENDED_PROPERTIES](/openspecs/sql_server_protocols/ms-ssas-t/5f3b307b-3552-4dbf-a850-b5d8472515e4)|Provides information about the ExtendedProperty objects in the model.|
|[TMSCHEMA_HIERARCHIES](/openspecs/sql_server_protocols/ms-ssas-t/57e09a17-5efa-4c58-9493-0c7927cf09f7)    |    Provides information about the Hierarchy objects in each table.     |
|[TMSCHEMA_KPIS](/openspecs/sql_server_protocols/ms-ssas-t/181291df-0d63-4855-9544-381a3f7258d0)     |    Provides information about the KPI objects in the model.     |
|[TMSCHEMA_LEVELS](/openspecs/sql_server_protocols/ms-ssas-t/292e24e9-9dc6-4ed0-b9dc-cd5a875e7475)     |   Provides information about the Level objects in each hierarchy.      |
|[TMSCHEMA_LINGUISTIC_METADATA](/openspecs/sql_server_protocols/ms-ssas-t/70143f9b-6c04-4140-a29c-f018d740cbce)|Provides information about the synonyms for objects in the model for a particular culture|
|[TMSCHEMA_MEASURES](/openspecs/sql_server_protocols/ms-ssas-t/960d4f92-49e9-4231-a39f-c7048e4ea63d)     |    Provides information about the Measure objects in each table.     |
|[TMSCHEMA_MODEL](/openspecs/sql_server_protocols/ms-ssas-t/2bef3023-5627-4343-8661-8df527a97bc1)    |  Specifies a Model object in the database.       |
|[TMSCHEMA_OBJECT_TRANSLATIONS](/openspecs/sql_server_protocols/ms-ssas-t/4d12c4b5-7d05-4a05-8693-e25c9354d36c)|Provides information about the translations of different objects for a culture.|
|[TMSCHEMA_PARTITIONS](/openspecs/sql_server_protocols/ms-ssas-t/c8fae079-ad92-47ab-b0eb-b78ea8db284c)     |     Provides information about the Partition objects in each table.    |
|[TMSCHEMA_PERSPECTIVE_COLUMNS](/openspecs/sql_server_protocols/ms-ssas-t/6d1265b5-1a99-4657-be29-63d4d3c501ab)     |   Provides information about the PerspectiveColumn objects in each PerspectiveTable object.      |
|[TMSCHEMA_PERSPECTIVE_HIERARCHIES](/openspecs/sql_server_protocols/ms-ssas-t/4192b2e7-f267-4963-8ac6-2b1c5e73bb72)     |  Provides information about the PerspectiveHierarchy objects in each PerspectiveTable object.       |
|[TMSCHEMA_PERSPECTIVE_MEASURES](/openspecs/sql_server_protocols/ms-ssas-t/57d7a206-3bb5-433f-b6c2-b83d4ded9ff1)     |    Provides information about the PerspectiveMeasure objects in each PerspectiveTable object.     |
|[TMSCHEMA_PERSPECTIVE_TABLES](/openspecs/sql_server_protocols/ms-ssas-t/fade6f94-89ad-4938-ba19-2925a8925b0f)     |    Provides information about the Table objects in a perspective.     |
|[TMSCHEMA_PERSPECTIVES](/openspecs/sql_server_protocols/ms-ssas-t/ad72d47f-88c7-465e-805d-fac84b8f3b06)     |     Provides information about the Perspective objects in the model.    |
|[TMSCHEMA_QUERY_GROUPS](/openspecs/sql_server_protocols/ms-ssas-t/e52c19a6-7ceb-4016-9236-313f372620a2)     |     Provides information about the QueryGroup objects in the tabular model.    |
|[TMSCHEMA_RELATIONSHIPS](/openspecs/sql_server_protocols/ms-ssas-t/bd5db04a-a5b1-4701-9b50-12aaf883630c)     |    Provides information about the Relationship objects in the model.     |
|[TMSCHEMA_ROLE_MEMBERSHIPS](/openspecs/sql_server_protocols/ms-ssas-t/f1f9923f-de9c-48ad-b810-6c9a278344b8)     |  Provides information about the RoleMembership objects in each role.      |
|[TMSCHEMA_ROLES](/openspecs/sql_server_protocols/ms-ssas-t/f91efbf1-dce0-4bc4-83bd-8519380a6aaa)    |   Provides information about the Role objects in the model.      |
|[TMSCHEMA_TABLE_PERMISSIONS](/openspecs/sql_server_protocols/ms-ssas-t/b17d88b9-86bf-4a69-95ec-1f5bec431bd4)    |    Provides information about the TablePermission objects in each role.     |
|[TMSCHEMA_TABLES](/openspecs/sql_server_protocols/ms-ssas-t/f5176f5c-188f-4d57-8477-e1928d814edb)     |   Provides information about the Table objects in the model.      |
|[TMSCHEMA_VARIATIONS](/openspecs/sql_server_protocols/ms-ssas-t/a1891d92-e2d0-4ad4-8168-df7f7360d248)|Provides information about the Variation objects in each column.|

### Rowsets described in the [MS-SSAS]: SQL Server Analysis Services Protocol

|Rowset|Description|  
|------------|-----------------|  
|[DBSCHEMA_CATALOGS](/openspecs/sql_server_protocols/ms-ssas/fc7cade7-becf-4ce9-aa25-96a714b04681)|Describes the catalogs that are accessible on the server.|  
|[DBSCHEMA_COLUMNS](/openspecs/sql_server_protocols/ms-ssas/9f26978e-bf0a-4a43-9d12-3c8c52b2e115)|Returns a row for each measure, each cube dimension attribute, and each schema rowset column, exposed as a column.|  
|[DBSCHEMA_PROVIDER_TYPES](/openspecs/sql_server_protocols/ms-ssas/68931d4b-1287-4f4f-826f-b5e21a866968)|Identifies the (base) data types supported by the server.|  
|[DBSCHEMA_TABLES](/openspecs/sql_server_protocols/ms-ssas/d0315410-a8a6-42b6-b8f9-f02e159810ff)|Returns dimensions, measure groups, or schema rowsets exposed as tables.|  
|[DISCOVER_CALC_DEPENDENCY](/openspecs/sql_server_protocols/ms-ssas/a59d3ced-51f1-4f26-a373-1faefb2fc278)| Returns information about the calculation dependency for an object that is specified in a Tabular database or in a DAX query that is executed against a Tabular database. </br></br>**Note:** The DISCOVER_CALC_DEPENDENCY rowset can be used to analyze dependencies and extract DAX expressions from semantic models hosted in Power BI by using XMLA endpoints. However, the DISCOVER_CALC_DEPENDENCY rowset does not include M dependencies for semantic models with Enhanced Metadata enabled, such as merged or appended M queries and M parameters. |  
|[DISCOVER_COMMAND_OBJECTS](/openspecs/sql_server_protocols/ms-ssas/8bf92e87-ccbf-4df3-b81c-08c6f734541e)|Provides resource usage and activity information about the objects in use by the referenced command.|  
|[DISCOVER_COMMANDS](/openspecs/sql_server_protocols/ms-ssas/94f5a668-857e-47c1-814e-ecd05ef93c96)|Provides resource usage and activity information about the currently executing or last executed commands in the opened connections on the server.|  
|[DISCOVER_CONNECTIONS](/openspecs/sql_server_protocols/ms-ssas/ae3b1e86-279f-4d45-aab8-b50efdda53d2)|Provides resource usage and activity information about the currently opened connections on the server.|  
|[DISCOVER_CSDL_METADATA](/openspecs/sql_server_protocols/ms-ssas/520fdc02-1b18-4534-a03b-4e97a26aa606)|Returns information about database metadata for in-memory databases.|  
|[DISCOVER_DATASOURCES](/openspecs/sql_server_protocols/ms-ssas/295e7c76-8fc0-45ef-a8a9-89dea02f4789)|Returns a list of the data sources that are available on the server.|
|[DISCOVER_DB_CONNECTIONS](/openspecs/sql_server_protocols/ms-ssas/46cfc9d3-fad7-4023-9c4b-caeb0adc6b3c)|Provides resource usage and activity information about the currently opened connections from the server to a database.|  
|[DISCOVER_DB_MEM_STATS](/openspecs/sql_server_protocols/ms-ssas/67789289-fe98-41f9-95d0-44cebe406a34)|Provides coarse-grained information about the memory trackers that are active on the server. The data is aggregated at the database and system level.|
|[DISCOVER_DIMENSION_STAT](/openspecs/sql_server_protocols/ms-ssas/2919437a-0c1f-490a-af4e-7402d716a687)|returns statistics on the specified dimension.|  
|[DISCOVER_ENUMERATORS](/openspecs/sql_server_protocols/ms-ssas/ead8766e-1c8e-42d7-b2c9-2763760441dd)|Returns a list of names, data types, and enumeration values of enumerators supported by the XMLA Provider for a specific data source.|  
|[DISCOVER_INSTANCES](/openspecs/sql_server_protocols/ms-ssas/79b8f6db-a5e5-47dd-9fae-334050948004)|Describes the instances on the server.|  
|[DISCOVER_JOBS](/openspecs/sql_server_protocols/ms-ssas/35371355-f3f0-42b8-ab6e-68be13398839)|Provides information about the active jobs executing on the server. A job is a part of a command that executes a specific task on behalf of the command.|  
|[DISCOVER_KEYWORDS &#40;XMLA&#41;](/openspecs/sql_server_protocols/ms-ssas/6bb30c01-71de-4c6a-96ce-a2628d988304)|Returns information about keywords that are reserved by the XMLA server.|  
|[DISCOVER_LITERALS](/openspecs/sql_server_protocols/ms-ssas/05cfba3b-a00e-48b9-9138-51910b7eb84d)|Returns information about literals supported by the server.|  
|[DISCOVER_LOCATIONS](/openspecs/sql_server_protocols/ms-ssas/ebfa86bd-6154-408f-bc2e-30c165f50f53)|Returns information about the contents of a backup file. |
|[DISCOVER_LOCKS](/openspecs/sql_server_protocols/ms-ssas/3b0b02b1-ca61-4673-87b1-03c893442a1d)|Provides information about the current standing locks on the server.|  
|[DISCOVER_MASTER_KEY](/openspecs/sql_server_protocols/ms-ssas/a402a982-3ee9-44b7-945d-48ad51648ea0)|Returns the server's master encryption key.|
|[DISCOVER_MEM_STATS](/openspecs/sql_server_protocols/ms-ssas/493ebbe6-34d3-4794-a86f-637058909b9e) |Provides fine-grained information about all the memory trackers that are active on the server.|
|[DISCOVER_MEMORYGRANT](/openspecs/sql_server_protocols/ms-ssas/dff0cece-b91f-431d-b277-fdedb766ca0f)|Returns a list of internal memory quota grants that are taken by jobs that are currently running on the server.|  
|[DISCOVER_MEMORYUSAGE](/openspecs/sql_server_protocols/ms-ssas/d9df279e-9610-43e3-a24d-5abb69462a97)|Returns the DISCOVER_MEMORYUSAGE statistics for various objects allocated by the server.|  
|[DISCOVER_OBJECT_ACTIVITY](/openspecs/sql_server_protocols/ms-ssas/8bcedfa1-47d0-4662-9956-575486f0ec15)|Provides resource usage per object since the start of the service.|  
|[DISCOVER_OBJECT_MEMORY_USAGE](/openspecs/sql_server_protocols/ms-ssas/cbac2750-a93e-448b-aa6c-75b622ae8d0d)|Returns the DISCOVER_MEMORYUSAGE statistics for various objects allocated by the server.|  
|[DISCOVER_PARTITION_DIMENSION_STAT](/openspecs/sql_server_protocols/ms-ssas/26e1111d-586a-4a3c-b1ba-ff8fadfdbd2a)|Returns statistics on the dimension that is associated with a partition.|  
|[DISCOVER_PARTITION_STAT](/openspecs/sql_server_protocols/ms-ssas/70be72d3-6f3a-4e07-838a-c47bc0a9fb8b)|Returns statistics on aggregations in a particular partition.|  
|[DISCOVER_PERFORMANCE_COUNTERS](/openspecs/sql_server_protocols/ms-ssas/ca07eb27-b7d8-42f5-a219-661c1ba6f119)|Returns the value of one or more specified performance counters. |  
|[DISCOVER_PROPERTIES](/openspecs/sql_server_protocols/ms-ssas/81f673a7-06b4-4372-8da7-becd5d63c23f)|Returns a list of information and values about the properties that are supported by the server for the specified data source.|  
|[DISCOVER_RING_BUFFERS](/openspecs/sql_server_protocols/ms-ssas/111a8403-9aef-44fb-8336-cb3ebba06df2)|Returns information about the current XEvent ring buffers on the server.|
|[DISCOVER_SCHEMA_ROWSETS](/openspecs/sql_server_protocols/ms-ssas/7046ee45-cc59-45e6-9a16-a0451aa57785)|Returns the names, restrictions, description, and other information for all Discover requests.|  
|[DISCOVER_SESSIONS](/openspecs/sql_server_protocols/ms-ssas/b85aa76d-d963-4f93-94c4-2ae6ea57f799)|Provides resource usage and activity information about the currently opened sessions on the server.|  
|[DISCOVER_STORAGE_TABLE_COLUMN_SEGMENTS](/openspecs/sql_server_protocols/ms-ssas/948d5135-5bf4-4cf7-82c5-3a38746c2fb8)|Returns information about the column segments used for storing data for in-memory tables.|  
|[DISCOVER_STORAGE_TABLE_COLUMNS](/openspecs/sql_server_protocols/ms-ssas/f95a2f76-b994-45c4-865c-21f63d9c9442)|Contains information about the columns used for representing the columns of an in-memory table.|  
|[DISCOVER_STORAGE_TABLES](/openspecs/sql_server_protocols/ms-ssas/eae69b5d-bd76-42d2-8429-665bf08d2cf0)|Returns statistics about in-memory tables available to the server.|  
|[DISCOVER_TRACE_COLUMNS](/openspecs/sql_server_protocols/ms-ssas/09059e99-89ec-4413-b303-b95b08f8e5a1)||  
|[DISCOVER_TRACE_DEFINITION_PROVIDERINFO](/openspecs/sql_server_protocols/ms-ssas/09059e99-89ec-4413-b303-b95b08f8e5a1)|Contains the DISCOVER_TRACE_COLUMNS schema rowset.|  
|[DISCOVER_TRACE_EVENT_CATEGORIES](/openspecs/sql_server_protocols/ms-ssas/429f1c81-1289-4e29-a0c1-50f2bf95b91b)|Contains the DISCOVER_TRACE_EVENT_CATEGORIES schema rowset.|  
|[DISCOVER_TRACES](/openspecs/sql_server_protocols/ms-ssas/5d427b58-c6ec-4a99-935d-c03bc57cb5fa)|Contains the DISCOVER_TRACES schema rowset.|  
|[DISCOVER_TRANSACTIONS](/openspecs/sql_server_protocols/ms-ssas/0ba57660-3c83-40e4-8c12-bedf648cc1bb)|Returns the current set of pending transactions on the system.|  
|[DISCOVER_XEVENT_TRACE_DEFINITION](/openspecs/sql_server_protocols/ms-ssas/7e74635a-51a0-4d1b-952a-672d03b9dbd4)|Provides information about the XEvent traces that are currently active on the server.|  
|[DISCOVER_XEVENT_PACKAGES](/openspecs/sql_server_protocols/ms-ssas/801e597e-da37-4079-a1ad-a99e5291f347)|Provides information about the XEvent packages that are described on the server.|
|[DISCOVER_XEVENT_OBJECTS](/openspecs/sql_server_protocols/ms-ssas/58789680-c1e7-4fd6-bacf-7b9ba6aa4708)|Provides information about the XEvent objects that are described on the server.|
|[DISCOVER_XEVENT_OBJECT_COLUMNS](/openspecs/sql_server_protocols/ms-ssas/a8b05878-cad4-43d8-ab54-3f0ff6d46e62)|Provides information about the schema of XEvent objects that are described on the server.|
|[DISCOVER_XEVENT_SESSIONS](/openspecs/sql_server_protocols/ms-ssas/3f9fbd9b-0813-468d-9943-778f908401ad)|Provides information about the current XEvent sessions on the server.|
|[DISCOVER_XEVENT_SESSION_TARGETS](/openspecs/sql_server_protocols/ms-ssas/793dffb6-e680-4d48-b10e-2ef360c8ddf0)|Provides information about the current XEvent session targets on the server.|
|[DISCOVER_XML_METADATA](/openspecs/sql_server_protocols/ms-ssas/51647299-75c7-471d-896f-a691e4114b18)|Returns a rowset with one row and one column. |
|[DMSCHEMA_MINING_COLUMNS](/openspecs/sql_server_protocols/ms-ssas/61b0c212-7eab-4a49-a39f-442eb6f10c1e)|Describes the individual columns of all described data mining models that are deployed on the server.|  
|[DMSCHEMA_MINING_FUNCTIONS](/openspecs/sql_server_protocols/ms-ssas/3ee70960-6963-49cd-9116-0159958b5044)|Describes the data mining functions that are supported by the data mining algorithms that are available on a server that is running Analysis Services.|  
|[DMSCHEMA_MINING_MODEL_CONTENT](/openspecs/sql_server_protocols/ms-ssas/fd3a6f7c-43ff-45e5-8ecc-8ab69add63e7)|Enables the client application to browse the content of a trained data mining model.|  
|[DMSCHEMA_MINING_MODEL_CONTENT_PMML](/openspecs/sql_server_protocols/ms-ssas/91457451-4593-4034-99e3-9b587306d5f8)|Returns the XML structure of the mining model. The format of the XML string follows the PMML 2.1 standard.|  
|[DMSCHEMA_MINING_MODEL_XML](/openspecs/sql_server_protocols/ms-ssas/b1b6efb8-03fd-401d-b2b5-ed392dd4d34c)|Returns the XML structure of the mining model. The format of the XML string follows the PMML 2.1 standard.|  
|[DMSCHEMA_MINING_MODELS](/openspecs/sql_server_protocols/ms-ssas/84ff3770-c663-41ae-bf02-86d731d6e83b)|Enumerates the data mining models that are deployed on the server.|  
|[DMSCHEMA_MINING_SERVICE_PARAMETERS](/openspecs/sql_server_protocols/ms-ssas/37b71935-7fe1-4a00-9ab8-4a055c4f32be)|Provides a list of parameters that can be used to configure the behavior of each data mining algorithm that is installed on the server.|  
|[DMSCHEMA_MINING_SERVICES](/openspecs/sql_server_protocols/ms-ssas/71853f87-8c7b-4fa9-91e7-c4ea6bbf2f3a)|Provides information about each data mining algorithm that the server supports.|  
|[DMSCHEMA_MINING_STRUCTURE_COLUMNS](/openspecs/sql_server_protocols/ms-ssas/2891a771-136a-4811-9012-b9dfe6d36309)|Describes the individual columns of all mining structures that are deployed on the server.|  
|[DMSCHEMA_MINING_STRUCTURES](/openspecs/sql_server_protocols/ms-ssas/9376c8e9-5c71-4928-92be-d54e8c1835da)|Enumerates information about the mining structures in the current catalog.|  
|[MDSCHEMA_ACTIONS](/openspecs/sql_server_protocols/ms-ssas/d68681cb-1a8c-4b79-aaf1-2e4288b90f5b)|Describes the actions that can be available to the client application.|
|[MDSCHEMA_CUBES](/openspecs/sql_server_protocols/ms-ssas/03530848-1a9a-48e4-b43d-c263b2961377)|Describes the structure of cubes within a database. Perspectives are also returned in this schema.|
|[MDSCHEMA_DIMENSIONS](/openspecs/sql_server_protocols/ms-ssas/0cbf7a49-a50b-4708-b2af-dcf1641f5f2b)|Describes the dimensions within a database.|  
|[MDSCHEMA_FUNCTIONS](/openspecs/sql_server_protocols/ms-ssas/e26ed3df-2fa0-405b-b694-9d8fa722d33d)|Returns information about the functions that are currently available for use in the DAX and MDX languages.|
|[MDSCHEMA_HIERARCHIES](/openspecs/sql_server_protocols/ms-ssas/244ae3cc-3440-44b8-ad09-77b866bb1a48)|Describes each hierarchy within a particular dimension.|  
|[MDSCHEMA_INPUT_DATASOURCES](/openspecs/sql_server_protocols/ms-ssas/1062ac71-dcde-439e-ba2f-e392a4ee8fe1)|Describes the data source objects described within the database.|  
|[MDSCHEMA_KPIS](/openspecs/sql_server_protocols/ms-ssas/3cf6c5d8-537d-4d42-a9a2-d6938af134f0)|Describes the KPIs within a database.|  
|[MDSCHEMA_LEVELS](/openspecs/sql_server_protocols/ms-ssas/bf5b4bd4-b5db-406b-b830-b3720e890b4a)|Describes each level within a particular hierarchy.|  
|[MDSCHEMA_MEASUREGROUP_DIMENSIONS](/openspecs/sql_server_protocols/ms-ssas/e6399481-a289-41f3-94d2-e081bf29e094)|Enumerates the dimensions of measure groups.|  
|[MDSCHEMA_MEASUREGROUPS](/openspecs/sql_server_protocols/ms-ssas/84d87d3a-9b92-4620-9ebf-e00fdc1e62bf)|Describes the measure groups within a database.|  
|[MDSCHEMA_MEASURES](/openspecs/sql_server_protocols/ms-ssas/ab8e721f-9b9c-4ba1-b105-37a5f200d67c)|Describes each measure.|  
|[MDSCHEMA_MEMBERS](/openspecs/sql_server_protocols/ms-ssas/e2df98e2-856f-402c-9313-f6a23920eb99)|Describes the members within a database.|  
|[MDSCHEMA_PROPERTIES](/openspecs/sql_server_protocols/ms-ssas/3a2dc7b3-79ba-4731-b662-fbf8501733cb)|Describes the properties of members and cell properties.|  
|[MDSCHEMA_SETS](/openspecs/sql_server_protocols/ms-ssas/0ae5d7cd-bae3-4448-9551-83c75209c0c3)|Describes any sets that are currently described in a database, including session-scoped sets.|  

> [!NOTE]
> STORAGES DMVs do not have a schema rowset described in the protocol.

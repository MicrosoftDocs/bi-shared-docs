---
title: "Retrieving Metadata from an Analytical Data Source | Microsoft Docs"
description: Learn how to retrieve two forms of metadata from an analytical data source by using ADOMD.NET.
ms.date: 02/14/2022
ms.service: analysis-services
ms.custom: adomd
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Retrieving Metadata from an Analytical Data Source
  Metadata is important to applications that retrieve and work with analytical data. When retrieving data from a relational data source, the dimensionality of such data is predictable, even with nested datasets. Result sets from a relational database are typically two-dimensional or scalar in structure. However, data retrieved from analytical data sources can be of variable dimensionality, organized along potentially deep hierarchies.  
  
 To handle the complexity of metadata retrieval from analytical data sources, ADOMD.NET provides two forms of metadata retrieval:  
  
 **The Object Model**  
 The ADOMD.NET object model is generally easier to use than schema rowsets. For most scenarios, you can access the metadata of various database objects just by using the object model. ADOMD.NET exposes the object model through the <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection>.  
  
 For more information: [Working with the ADOMD.NET Object Model](retrieving-metadata-working-with-adomd-net-object-model.md)  
  
 **Schema Rowsets**  
 A complete, but more difficult approach to retrieving metadata is through using schema rowsets. A schema rowset is an OLE DB rowset that encapsulates the description for all objects of a particular type in the database. Schema information in an analytical data source includes databases or catalogs available from the data source, cubes and mining models in a database, roles that exist for cubes at the data source, and so on. This metadata can be retrieved by using the <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.GetSchemaDataSet%2A> method, passing in either a **GUID** or an XML for Analysis (XMLA) name.  
  
 For more information: [Working with Schema Rowsets in ADOMD.NET](retrieving-metadata-working-with-schema-rowsets.md)  
  
 Each of these metadata retrieval methods access different types of metadata. The following table describes the different metadata available for each method, and the methods used to access it.  
  
|GUID (used in Schema Rowsets)|XMLA Name (used in Schema Rowsets)|ADOMD.NET Object Model|  
|-------------------------------------|------------------------------------------|----------------------------|  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Actions>|MDSCHEMA_ACTIONS Rowset||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Catalogs>|DBSCHEMA_CATALOGS Rowset||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Columns>|DBSCHEMA_COLUMNS Rowset||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Connections>|DISCOVER_CONNECTIONS||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Cubes>|MDSCHEMA_CUBES Rowset|AdomdConnection.Cubes|  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.DataSources>|DISCOVER_DATASOURCES Rowset||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.DBConnections>|DISCOVER_DB_CONNECTIONS||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Dimensions>|MDSCHEMA_DIMENSIONS Rowset|AdomdConnection.Cubes[].Dimensions|  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.DimensionStat>|DISCOVER_DIMENSION_STAT||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Enumerators>|DISCOVER_ENUMERATORS Rowset||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Functions>|MDSCHEMA_FUNCTIONS Rowset||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Hierarchies>|MDSCHEMA_HIERARCHIES Rowset|AdomdConnection.Cubes[].Dimensions[].Hierarchies|  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.InputDataSources>|MDSCHEMA_INPUT_DATASOURCES Rowset||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Instances>|DISCOVER_INSTANCES Rowset||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Jobs>|DISCOVER_JOBS||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Keywords>|DISCOVER_KEYWORDS Rowset &#40;OLE DB for OLAP&#41;||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Kpis>|MDSCHEMA_KPIS Rowset|AdomdConnection.Cubes[].KPIs|  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Levels>|MDSCHEMA_LEVELS Rowset|AdomdConnection.Cubes[].Dimensions[].Hierarchies[].Levels|  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Literals>|DISCOVER_LITERALS Rowset||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Locations>|DISCOVER_LOCATIONS||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Locks>|DISCOVER_LOCKS||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.MasterKey>|DISCOVER_MASTER_KEY||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.MeasureGroupDimensions>|MDSCHEMA_MEASUREGROUP_DIMENSIONS Rowset||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.MeasureGroups>|MDSCHEMA_MEASUREGROUPS Rowset||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Measures>|MDSCHEMA_MEASURES Rowset|AdomdConnection.Cubes[].Measures|  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.MemberProperties>|MDSCHEMA_PROPERTIES Rowset|PropertyCollection available from most major ADOMD.NET objects.|  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Members>|MDSCHEMA_MEMBERS Rowset|AdomdConnection.Cubes[].Dimensions[].Hierarchies[].Levels[].GetMembers()|  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.MemoryGrant>|DISCOVER_MEMORYGRANT||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.MemoryUsage>|DISCOVER_MEMORYUSAGE||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.MiningColumns>|DMSCHEMA_MINING_COLUMNS Rowset|AdomdConnection.MiningModels[].MiningModelColumns|  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.MiningFunctions>|DMSCHEMA_MINING_FUNCTIONS Rowset||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.MiningModelContent>|DMSCHEMA_MINING_MODEL_CONTENT Rowset|AdomdConnection.MiningModels[].MiningContentNodes|  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.MiningModelContentPmml>|DMSCHEMA_MINING_MODEL_CONTENT_PMML Rowset||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.MiningModels>|DMSCHEMA_MINING_MODELS Rowset|AdomdConnection.MiningModels|  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.MiningModelXml>|DMSCHEMA_MINING_MODEL_XML Rowset||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.MiningServiceParameters>|DMSCHEMA_MINING_SERVICE_PARAMETERS Rowset|AdomdConnection.MiningServices[].MiningServiceParameters|  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.MiningServices>|DMSCHEMA_MINING_SERVICES Rowset|AdomdConnection.MiningServices|  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.MiningStructureColumns>|DMSCHEMA_MINING_STRUCTURE_COLUMNS Rowset|AdomdConnection.MiningStructures[].MiningStructureColumns|  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.MiningStructures>|DMSCHEMA_MINING_STRUCTURES Rowset|AdomdConnection.MiningStructures|  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.PartitionDimensionStat>|DISCOVER_PARTITION_DIMENSION_STAT||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.PartitionStat>|DISCOVER_PARTITION_STAT||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.PerformanceCounters>|DISCOVER_PERFORMANCE_COUNTERS||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.ProviderTypes>|DBSCHEMA_PROVIDER_TYPES Rowset||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.SchemaRowsets>|DISCOVER_SCHEMA_ROWSETS Rowset||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Sessions>|DISCOVER_SESSIONS||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Sets>|MDSCHEMA_SETS Rowset|AdomdConnection.Cubes[].NamedSets|  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Tables>|DBSCHEMA_TABLES Rowset||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.TablesInfo>|DBSCHEMA_TABLES_INFO||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.TraceColumns>|DISCOVER_TRACE_COLUMNS||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.TraceDefinitionProviderInfo>|DISCOVER_TRACE_DEFINITION_PROVIDERINFO||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.TraceEventCategories>|DISCOVER_TRACE_EVENT_CATEGORIES||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Traces>|DISCOVER_TRACES||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.Transactions>|DISCOVER_TRANSACTIONS||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.XmlaProperties>|DISCOVER_PROPERTIES Rowset||  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid.XmlMetadata>|DISCOVER_XML_METADATA Rowset||  

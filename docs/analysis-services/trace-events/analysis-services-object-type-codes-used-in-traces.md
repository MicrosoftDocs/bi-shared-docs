---
title: "Analysis Services object type codes used in traces | Microsoft Docs"
description: Learn about the object type of each object in a data model. These codes appear in trace logs and are used to identify the type of object associated with a particular lock.
ms.date: 07/19/2021
ms.service: analysis-services
ms.custom: trace-events
ms.topic: reference
---
# Analysis Services object type codes used in traces

  This page lists the object type (a six digit number) of each object in a data model. These codes appear in trace logs and are used to identify the type of object associated with a particular lock. For example, a lock timeout on a database will indicate the object type 100002, which is the Database object type.  
  
> [!NOTE]  
>  There are more codes listed below than what will actually appear in a trace log. The list below is a comprehensive list of type codes for every object, but only objects that take a lock will present an object type code in a trace log.  
  
## Tabular object types

|Object type|Object name|  
|-----------------|-----------------|  
|801002|Database|  
|802010|Model|  
|802011|Datasource|  
|802012|Table|  
|802013|Column|  
|802014|AttributeHierarchy|  
|802015|Partition|  
|802016|Relationship|  
|802017|Measure|  
|802018|Hierarchy|  
|802019|Level|  
|802020|Annotation|  
|802021|KPI|  
|802022|Culture|  
|802023|ObjectTranslation|  
|802024|LinguisticMetadata|  
|802038|Perspective|  
|802039|PerspectiveTable|  
|802040|PerspectiveTableColumn|  
|802041|PerspectiveTableHierarchy|  
|802042|PerspectiveTableMeasure|  
|802043|Role|  
|802044|RoleMembership|  
|802045|TablePermission|  
|802046|Variation|  
|802051|ColumnPermission|  
|802052|DetailRowsDefinition|  
|802055|AlternateOf|

## Multidimensional object types
  
|Object type|Object name|  
|-----------------|-----------------|  
|100000|Server|  
|100001|Command|  
|100002|Database|  
|100003|DataSource|  
|100004|DatabasePermission|  
|100005|Role|  
|100006|Dimension|  
|100007|DimensionAttribute|  
|100008|Hierarchy|  
|100009|Level|  
|100010|Cube|  
|100011|CubePermission|  
|100012|CubeDimension|  
|100013|CubeAttribute|  
|100014|CubeHierarchy|  
|100016|MeasureGroup|  
|100017|MeasureGroupDimension|  
|100018|MeasureGroupAttribute|  
|100020|Measure|  
|100021|Partition|  
|100025|AggregationDesign|  
|100026|AggregationDesignDimension|  
|100027|AggregationDesignAttribute|  
|100028|Aggregation|  
|100029|AggregationDimension|  
|100030|AggregationAttribute|  
|100032|MiningStructure|  
|100033|MiningStructureColumn|  
|100037|MiningModel|  
|100038|MiningModelColumn|  
|100039|AlgorithmParameter|  
|100041|MiningModelPermission|  
|100042|DimensionPermission|  
|100043|MiningStructurePermission|  
|100044|Assembly|  
|100045|DatabaseRole|  
|100046|AttributePermission|  
|100047|CubeAttributePermission|  
|100048|CellPermission|  
|100049|CubeDimensionPermission|  
|100050|Trace|  
|100051|ServerAssembly|  
|100052|CubeAssembly|  
|100053|Command|  
|100054|KPI|  
|100055|DataSourceView|  
|100056|Perspective|  
|100100|CommandCollection|  
|100101|DatabaseCollection|  
|100102|DataSourceCollection|  
|100103|DatabasePermission|  
|100104|RoleCollection|  
|100105|DimensionCollection|  
|100106|DimensionAttributeCollection|  
|100107|HierarchyCollection|  
|100108|LevelCollection|  
|100109|CubeCollection|  
|100110|CubePermissionCollection|  
|100111|CubeDimensionCollection|  
|100112|CubeAttributeCollection|  
|100113|CubeHierarchyCollection|  
|100115|MeasureGroupCollection|  
|100116|MeasureGroupDimensionCollection|  
|100117|MeasureGroupAttributeCollection|  
|100119|MeasureCollection|  
|100120|PartitionCollection|  
|100124|AggregationDesignCollection|  
|100125|AggregationDesignDimensionCollection|  
|100126|AggregationDesignAttributeCollection|  
|100127|AggregationCollection|  
|100128|AggregationDimensionCollection|  
|100129|AggregationAttributeCollection|  
|100131|MiningStructureCollection|  
|100132|MiningStructureColumnCollection|  
|100136|MiningModelCollection|  
|100137|MiningModelColumnCollection|  
|100138|AlgorithmParameterCollection|  
|100140|MiningModelPermissionCollection|  
|100141|DimensionPermissionCollection|  
|100142|MiningStructurePermissionCollection|  
|100143|AssemblyCollection|  
|100144|DatabaseRoleCollecction|  
|100145|AttributePermissionCollection|  
|100146|CubeAttributePermissionCollection|  
|100147|CellPermissionCollection|  
|100148|CubeDimensionPermissionCollection|  
|100149|TraceCollection|  
|100150|ServerAssemblyCollection|  
|100151|CubeAssemblyCollection|  
|100152|CommandCollection|  
|100153|KpiCollection|  
|100154|DataSourceViewCollection|  
|100155|PerspectiveCollection|  

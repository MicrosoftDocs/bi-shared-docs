---
title: "Collections (ASSL) | Microsoft Docs"
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Collections (ASSL)

  This reference section contains syntax and usage information for each element that acts as a collection in the Analysis Services Scripting Language (ASSL) schema.  
  
 Although the ASSL schema contains only XML elements, from a developer's point of view, the elements described in this section correspond to collections of objects, such as the **Dimensions** and **Cubes** collections.  
  
 Collections are mostly collections of object elements, in which a plural noun designates the collection (for examples, **Cubes**), and the collection contains elements designated by the same noun in the singular (for example, **Cube**).  
  
 In some cases, the schema does not adhere to this general rule. For example, the **ClassifiedColumns** collection contains **ClassifiedColumnID** elements.  
  
 In other cases, a collection contains elements that correspond to object properties, not to objects. For example, the **Aliases** collection contains **Alias** properties, each of which is a simple string value.  
  
|Element|Description|  
|-------------|-----------------|  
|[Accounts Element &#40;ASSL&#41;](collections/accounts-element-assl.md)|Contains the collection of account types that are defined in a [Database](objects/database-element-assl.md) element.|  
|[Actions Element &#40;ASSL&#41;](collections/actions-element-assl.md)|Contains the collection of actions for a [Cube](objects/cube-element-assl.md) or [Perspective](objects/perspective-element-assl.md) element.|  
|[AggregationDesigns Element &#40;ASSL&#41;](collections/aggregationdesigns-element-assl.md)|Contains the collection of aggregation designs that can be shared across multiple partitions in a database.|  
|[AggregationInstances Element &#40;ASSL&#41;](collections/aggregationinstances-element-assl.md)|Contains the collection of aggregation instances that are defined in a [Partition](objects/partition-element-assl.md) element.|  
|[Aggregations Element &#40;ASSL&#41;](collections/aggregations-element-assl.md)|Contains the collection of aggregations defined for an [AggregationDesign](objects/aggregationdesign-element-assl.md) element.|  
|[AlgorithmParameters Element &#40;ASSL&#41;](collections/algorithmparameters-element-assl.md)|Contains the collection of parameters for the algorithm used by a [MiningModel](objects/miningmodel-element-assl.md) element.|  
|[Aliases Element &#40;ASSL&#41;](collections/aliases-element-assl.md)|Contains the collection of [Alias](properties/alias-element-assl.md) elements associated with an [Account](objects/account-element-assl.md) element|  
|[AllMemberTranslations Element &#40;ASSL&#41;](collections/allmembertranslations-element-assl.md)|Contains the collection of [Translation](objects/translation-element-assl.md) elements for the caption of the All member of a [Hierarchy](objects/hierarchy-element-assl.md) element.|  
|[Annotations Element &#40;ASSL&#41;](collections/annotations-element-assl.md)|Contains the collection of [Annotation](objects/annotation-element-assl.md) elements associated with the parent element.|  
|[Assemblies Element &#40;ASSL&#41;](collections/assemblies-element-assl.md)|Contains the collection of [Assembly](objects/assembly-element-assl.md) elements associated with a [Server](objects/server-element-assl.md) element or a [Database](objects/database-element-assl.md) element.|  
|[AttributeAllMemberTranslations Element &#40;ASSL&#41;](collections/attributeallmembertranslations-element-assl.md)|Contains the collection of translations for the caption of the All member of the dimension.|  
|[AttributePermissions Element &#40;ASSL&#41;](collections/attributepermissions-element-assl.md)|Contains the collection of attribute permissions for an individual [Role](objects/role-element-assl.md) element on a specific dimension of a [Cube](objects/cube-element-assl.md) element.|  
|[AttributeRelationships Element &#40;ASSL&#41;](collections/attributerelationships-element-assl.md)|Contains the collection of [AttributeRelationship](objects/attributerelationship-element-assl.md) elements for the attribute.|  
|[Attributes Element &#40;ASSL&#41;](collections/attributes-element-assl.md)|Contains the collection of attributes for the associated dimension.|  
|[Blocks Element &#40;ASSL&#41;](collections/blocks-element-assl.md)|Contains the collection of blocks of binary data that represent the binary contents of a [ClrAssemblyFile](data-type/clrassemblyfile-data-type-assl.md) element.|  
|[CalculationProperties Element &#40;ASSL&#41;](collections/calculationproperties-element-assl.md)|Contains the collection of [CalculationProperty](objects/calculationproperty-element-assl.md) elements associated with an [MdxScript](objects/mdxscript-element-assl.md) element.|  
|[Calculations Element &#40;ASSL&#41;](collections/calculations-element-assl.md)|Contains the collection of [PerspectiveCalculation](data-type/perspectivecalculation-data-type-assl.md) elements associated with a [Perspective](objects/perspective-element-assl.md) element.|  
|[CellPermissions Element &#40;ASSL&#41;](collections/cellpermissions-element-assl.md)|Contains the collection of permissions for cells in the associated [Cube](objects/cube-element-assl.md) element.|  
|[ClassifiedColumns Element &#40;ASSL&#41;](collections/classifiedcolumns-element-assl.md)|Contains the collection of related columns that are classified by the [ScalarMiningStructureColumn](data-type/scalarminingstructurecolumn-data-type-assl.md) element.|  
|[Columns Element &#40;ASSL&#41;](collections/columns-element-assl.md)|Contains the collection of columns associated with the parent element.|  
|[Commands Element &#40;ASSL&#41;](collections/commands-element-assl.md)|Contains the collection of [Command](objects/command-element-assl.md) elements associated with an [MdxScript](objects/mdxscript-element-assl.md) element.|  
|[CubePermissions Element &#40;ASSL&#41;](collections/cubepermissions-element-assl.md)|Contains the collection of permissions applicable to a [Cube](objects/cube-element-assl.md) element.|  
|[Cubes Element &#40;ASSL&#41;](collections/cubes-element-assl.md)|Contains the collection of [Cube](objects/cube-element-assl.md) elements associated with a [Database](objects/database-element-assl.md) element.|  
|[DatabasePermissions Element &#40;ASSL&#41;](collections/databasepermissions-element-assl.md)|Contains the collection of [DatabasePermission](objects/databasepermission-element-assl.md) elements associated with a [Database](objects/database-element-assl.md) element.|  
|[Databases Element &#40;ASSL&#41;](collections/databases-element-assl.md)|Contains the collection of [Database](objects/database-element-assl.md) elements associated with a [Server](objects/server-element-assl.md) element.|  
|[DataSources Element &#40;ASSL&#41;](collections/datasources-element-assl.md)|Contains the collection of [DataSourcePermission](objects/datasourcepermission-element-assl.md) elements associated with a [DataSource](data-type/datasource-data-type-assl.md) data type.|  
|[DataSourcePermissions Element &#40;ASSL&#41;](collections/datasourcepermissions-element-assl.md)|Contains the collection of [DataSource](objects/datasource-element-assl.md) elements associated with a [Database](objects/database-element-assl.md) element.|  
|[DataSourceViews Element &#40;ASSL&#41;](collections/datasourceviews-element-assl.md)|Contains the collection of [DataSourceView](objects/datasourceview-element-assl.md) elements associated with a [Database](objects/database-element-assl.md) element.|  
|[DimensionPermissions Element &#40;ASSL&#41;](collections/dimensionpermissions-element-assl.md)|Contains the collection of permissions applicable to a [Dimension](objects/dimension-element-assl.md) element or a [CubePermission](objects/cubepermission-element-assl.md) element.|  
|[Dimensions Element &#40;ASSL&#41;](collections/dimensions-element-assl.md)|Contains the collection of dimensions associated with the parent element.|  
|[Events Element &#40;ASSL&#41;](collections/events-element-assl.md)|Defines the collection of Event elements to be captured by a [Trace](objects/trace-element-assl.md).|  
|[Files Element &#40;ASSL&#41;](collections/files-element-assl.md)|Contains the collection of [File](objects/file-element-assl.md) elements that make up a [ClrAssembly](data-type/clrassembly-data-type-assl.md) element.|  
|[ForeignKeyColumns Element &#40;ASSL&#41;](collections/foreignkeycolumns-element-assl.md)|Contains the collection of columns that identify the join to the parent table for a relational data source.|  
|[Groups Element &#40;ASSL&#41;](collections/groups-element-assl.md)|Contains the collection of groups of members bound to an attribute.|  
|[Hierarchies Element &#40;ASSL&#41;](collections/hierarchies-element-assl.md)|Contains the collection of [Hierarchy](objects/hierarchy-element-assl.md) elements associated with the parent element.|  
|[IncrementalProcessingNotifications Element &#40;ASSL&#41;](collections/incrementalprocessingnotifications-element-assl.md)|Contains the collection of [IncrementalProcessingNotification](objects/incrementalprocessingnotification-element-assl.md) elements that provide information to the [ProactiveCaching](objects/proactivecaching-element-assl.md) element about queries to execute to determine the progress of incremental processing.|  
|[KeyColumns Element &#40;ASSL&#41;](collections/keycolumns-element-assl.md)|Contains the collection of [KeyColumn](objects/keycolumn-element-assl.md) element definitions for a parent object.|  
|[Kpis Element &#40;ASSL&#41;](collections/kpis-element-assl.md)|Contains the collection of [Kpi](objects/kpi-element-assl.md) elements associated with the parent element.|  
|[Levels Element &#40;ASSL&#41;](collections/levels-element-assl.md)|Contains the collection of [Level](objects/level-element-assl.md) elements in a [Hierarchy](objects/hierarchy-element-assl.md) element.|  
|[MdxScripts Element &#40;ASSL&#41;](collections/mdxscripts-element-assl.md)|Contains the collection of [MdxScript](objects/mdxscript-element-assl.md) elements associated with a [Cube](objects/cube-element-assl.md) element.|  
|[MeasureGroups Element &#40;ASSL&#41;](collections/measuregroups-element-assl.md)|Contains the collection of [MeasureGroup](objects/measuregroup-element-assl.md) elements associated with the parent element.|  
|[Measures Element &#40;ASSL&#41;](collections/measures-element-assl.md)|Contains the collection of [Measure](objects/measure-element-assl.md) elements associated with the parent element.|  
|[Members Element &#40;ASSL&#41;](collections/members-element-assl.md)|Contains the collection of [Member](objects/member-element-assl.md) elements of the parent element.|  
|[MiningModelPermissions Element &#40;ASSL&#41;](collections/miningmodelpermissions-element-assl.md)|Contains the collection of permissions for a [MiningModel](objects/miningmodel-element-assl.md) element.|  
|[MiningModels Element &#40;ASSL&#41;](collections/miningmodels-element-assl.md)|Contains the collection of [MiningModel](objects/miningmodel-element-assl.md) elements associated with a [MiningStructure](objects/miningstructure-element-assl.md).|  
|[MiningStructurePermissions Element &#40;ASSL&#41;](collections/miningstructurepermissions-element-assl.md)|Contains the collection of permissions on a [MiningStructure](objects/miningstructure-element-assl.md) element.|  
|[MiningStructures Element &#40;ASSL&#41;](collections/miningstructures-element-assl.md)|Contains the collection of [MiningStructure](objects/miningstructure-element-assl.md) elements in a [Database](objects/database-element-assl.md) element.|  
|[ModelingFlags Element &#40;ASSL&#41;](collections/modelingflags-element-assl.md)|Contains the collection of [ModelingFlag](objects/modelingflag-element-assl.md) elements for a column in a [MiningStructure](objects/miningstructure-element-assl.md) or a [MiningModel](objects/miningmodel-element-assl.md).|  
|[NamingTemplateTranslations Element &#40;ASSL&#41;](collections/namingtemplatetranslations-element-assl.md)|Provides a collection of localized translations for the [NamingTemplate](properties/namingtemplate-element-assl.md) element of the parent [DimensionAttribute](data-type/dimensionattribute-data-type-assl.md).|  
|[Partitions Element &#40;ASSL&#41;](collections/partitions-element-assl.md)|Contains the collection of [Partition](objects/partition-element-assl.md) elements used by a [MeasureGroup](objects/measuregroup-element-assl.md) element, or the collection of partition bindings that make up an out-of-line [MeasureGroupBinding](data-type/measuregroupbinding-data-type-out-of-line-assl.md) element.|  
|[Perspectives Element &#40;ASSL&#41;](collections/perspectives-element-assl.md)|Contains the collection of [Perspective](objects/perspective-element-assl.md) elements associated with a [Cube](objects/cube-element-assl.md) element.|  
|[QueryNotifications Element &#40;ASSL&#41;](collections/querynotifications-element-assl.md)|Contains the collection of [QueryNotification](objects/querynotification-element-assl.md) elements that provide information to the [ProactiveCaching](objects/proactivecaching-element-assl.md) element about queries to execute to determine whether a data source has been modified.|  
|[ReportFormatParameters Element &#40;ASSL&#41;](collections/reportformatparameters-element-assl.md)|Contains the collection of [ReportFormatParameter](objects/reportformatparameter-element-asl.md) elements for a [ReportAction](data-type/reportaction-data-type-assl.md) element.|  
|[ReportParameters Element &#40;ASSL&#41;](collections/reportparameters-element-assl.md)|Contains the collection of [ReportParameter](objects/reportparameter-element-assl.md) elements for a [ReportAction](data-type/reportaction-data-type-assl.md) element.|  
|[Roles Element &#40;ASSL&#41;](collections/roles-element-assl.md)|Contains the collection of [Role](objects/role-element-assl.md) elements defined under the parent element.|  
|[ServerProperties Element &#40;ASSL&#41;](collections/serverproperties-element-assl.md)|Contains the collection of [ServerProperty](objects/serverproperty-element-assl.md) elements associated with a [Server](objects/server-element-assl.md) element.|  
|[TableNotifications Element &#40;ASSL&#41;](collections/tablenotifications-element-assl.md)|Contains the collection of [TableNotification](objects/tablenotification-element-assl.md) elements that provide information for the [ProactiveCaching](objects/proactivecaching-element-assl.md) element about tables or views in a data source that have been modified.|  
|[Traces Element &#40;ASSL&#41;](collections/traces-element-assl.md)|Contains the collection of [Trace](objects/trace-element-assl.md) elements associated with a [Server](objects/server-element-assl.md) element.|  
|[Translations Element &#40;ASSL&#41;](collections/translations-element-assl.md)|Contains the collection of [Translation](objects/translation-element-assl.md) elements associated with the parent element.|  
|[UnknownMemberTranslations Element &#40;ASSL&#41;](collections/unknownmembertranslations-element-assl.md)|Contains the collection of translations for the caption of the [UnknownMember](properties/unknownmember-element-assl.md) element of a dimension.|  
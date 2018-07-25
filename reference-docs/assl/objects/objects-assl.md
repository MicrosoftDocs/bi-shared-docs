---
title: "Objects (ASSL) | Microsoft Docs"
ms.date: 07/25/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Objects (ASSL)

  This reference section contains syntax and usage information for each element that acts as an object in the Analysis Services Scripting Language (ASSL) schema.  
  
 Although the ASSL schema contains only XML elements, from a developer's point of view, the elements described in this section correspond to objects, such as **Database**, **Cube**, and **Dimension** objects, in the hierarchy of objects contained by an instance of Analysis Services.  
  
 Objects are never leaf-level elements in the ASSL schema, but have child elements and elements that correspond to object properties.  
  
 In a few cases, a leaf-level element in the schema that may appear to be a property is classified as an object because the element's type is an object type. For example, the **Source** of a **Dimension** object is of type **DimensionBinding**.  
  
## In This Section  
  
|Element|Description|  
|-------------|-----------------|  
|[Account Element &#40;ASSL&#41;](../objects/account-element-assl.md)|Contains details about an account type within a [Database](../objects/database-element-assl.md) element.|  
|[Action Element &#40;ASSL&#41;](../objects/action-element-assl.md)|Contains information about an action available in a [Cube](../objects/cube-element-assl.md) element or a [Perspective](../objects/perspective-element-assl.md) element.|  
|[Aggregation Element &#40;ASSL&#41;](../objects/aggregation-element-assl.md)|Defines a single aggregation for a [Partition](../objects/partition-element-assl.md) element.|  
|[AggregationDesign Element &#40;ASSL&#41;](../objects/aggregationdesign-element-assl.md)|Defines a set of aggregation definitions that can be shared across multiple partitions in a database.|  
|[AggregationInstance Element &#40;ASSL&#41;](../objects/aggregationinstance-element-assl.md)|Defines an aggregation instance for a partition.|  
|[AlgorithmParameter Element &#40;ASSL&#41;](../objects/algorithmparameter-element-assl.md)|Defines a parameter for the algorithm used by a [MiningModel](../objects/miningmodel-element-assl.md) element.|  
|[AllMemberTranslation Element &#40;ASSL&#41;](../objects/allmembertranslation-element-assl.md)|Contains a translation for the caption of the All member of a [Hierarchy](../objects/hierarchy-element-assl.md) element.|  
|[Annotation Element &#40;ASSL&#41;](../objects/annotation-element-assl.md)|Contains elements that are used to extend the ASSL schema.|  
|[Assembly Element &#40;ASSL&#41;](../objects/assembly-element-assl.md)|Represents a Microsoft .NET Framework assembly or a COM dynamic link library (DLL) associated with a [Server](../objects/server-element-assl.md) element or a [Database](../objects/database-element-assl.md) element.|  
|[Attribute Element &#40;ASSL&#41;](../objects/attribute-element-assl.md)|Contains the description of an attribute.|  
|[AttributeAllMemberTranslation Element &#40;ASSL&#41;](../objects/attributeallmembertranslation-element-assl.md)|Contains a translation for the caption of the All member of a [DimensionAttribute](data-type/dimensionattribute-data-type-assl.md) element.|  
|[AttributePermission Element &#40;ASSL&#41;](../objects/attributepermission-element-assl.md)|Defines the permissions that members of a [Role](../objects/role-element-assl.md) element have on the attributes of an individual dimension in a [Cube](../objects/cube-element-assl.md) element.|  
|[AttributeRelationship Element &#40;ASSL&#41;](../objects/attributerelationship-element-assl.md)|Provides details about the relationship between two attributes.|  
|[Block Element &#40;ASSL&#41;](../objects/block-element-assl.md)|Contains all or a portion of the binary contents of a [ClrAssemblyFile](data-type/clrassemblyfile-data-type-assl.md) element.|  
|[Calculation Element &#40;ASSL&#41;](../objects/calculation-element-assl.md)|Asssociates a calculation with a [Perspective](../objects/perspective-element-assl.md) element.|  
|[CalculationProperty Element &#40;ASSL&#41;](../objects/calculationproperty-element-assl.md)|Contains a collection of user interface properties for a calculation used in an [MdxScript](../objects/mdxscript-element-assl.md) element.|  
|[CaptionColumn Element &#40;ASSL&#41;](../objects/captioncolumn-element-assl.md)|Defines the column that provides the caption for the attribute.|  
|[CellPermission Element &#40;ASSL&#41;](../objects/cellpermission-element-assl.md)|Describes the permissions that members of a [Role](../objects/role-element-assl.md) element have on individual cells within a [Cube](../objects/cube-element-assl.md) element.|  
|[Column Element &#40;ASSL&#41;](../objects/column-element-assl.md)|Describes a column in the collection of columns associated with the parent element.|  
|[Command Element &#40;ASSL&#41;](../objects/command-element-assl.md)|Defines a command that is available for use within the context of the parent element of the Commands collection.|  
|[Cube Element &#40;ASSL&#41;](../objects/cube-element-assl.md)|Defines a regular, virtual, or linked cube in anAnalysis Services [Database](../objects/database-element-assl.md) element.|  
|[CubePermission Element &#40;ASSL&#41;](../objects/cubepermission-element-assl.md)|Defines the permissions of the members of a particular [Role](../objects/role-element-assl.md) element in a specific [Cube](../objects/cube-element-assl.md) element.|  
|[CustomRollupColumn Element &#40;ASSL&#41;](../objects/customrollupcolumn-element-assl.md)|Defines the details of the column that provide a custom rollup formula.|  
|[CustomRollupPropertiesColumn Element &#40;ASSL&#41;](../objects/customrolluppropertiescolumn-element-assl.md)|Defines the details of a column that provide the properties of a custom rollup formula.|  
|[Data Element &#40;ASSL&#41;](../objects/data-element-assl.md)|Contains (in the collection of child **Block** elements) the binary contents of a [ClrAssemblyFile](data-type/clrassemblyfile-data-type-assl.md) element.|  
|[Database Element &#40;ASSL&#41;](../objects/database-element-assl.md)|Defines anAnalysis Services database.|  
|[DatabasePermission Element &#40;ASSL&#41;](../objects/databasepermission-element-assl.md)|Defines the default permissions in a [Database](../objects/database-element-assl.md) element for a specific [Role](../objects/role-element-assl.md) element.|  
|[DataSource Element &#40;ASSL&#41;](../objects/datasource-element-assl.md)|Defines a data source in a [Database](../objects/database-element-assl.md) element.|  
|[DataSourcePermission Element &#40;ASSL&#41;](../objects/datasourcepermission-element-assl.md)|Defines the default permissions in a [DataSource](data-type/datasource-data-type-assl.md) data type for a specific [Role](../objects/role-element-assl.md) element.|  
|[DataSourceView Element &#40;ASSL&#41;](../objects/datasourceview-element-assl.md)|Defines a data source view used by a [Database](../objects/database-element-assl.md) element.|  
|[Dimension Element &#40;ASSL&#41;](../objects/dimension-element-assl.md)|Defines a dimension.|  
|[DimensionPermission Element &#40;ASSL&#41;](../objects/dimensionpermission-element-assl.md)|Defines the permissions that belong to a particular [Role](../objects/role-element-assl.md) element for a specific database dimension or cube dimension.|  
|[ErrorConfiguration Element &#40;ASSL&#41;](../objects/errorconfiguration-element-assl.md)|Specifies settings for handling errors that can occur when the parent element is processed.|  
|[Event Element &#40;ASSL&#41;](../objects/event-element-assl.md)|Defines an event to be captured as part of a [Trace](../objects/trace-element-assl.md) element.|  
|[File Element &#40;ASSL&#41;](../objects/file-element-assl.md)|Defines one of the files that compose a [ClrAssembly](data-type/clrassembly-data-type-assl.md) element.|  
|[ForeignKeyColumn Element &#40;ASSL&#41;](../objects/foreignkeycolumn-element-assl.md)|Identifies the join to a parent table for a relational data source.|  
|[Group Element &#40;ASSL&#41;](../objects/group-element-assl.md)|Defines a group of members bound to an attribute.|  
|[Hierarchy Element &#40;ASSL&#41;](../objects/hierarchy-element-assl.md)|Defines a hierarchy in a dimension.|  
|[IncrementalProcessingNotification Element &#40;ASSL&#41;](../objects/incrementalprocessingnotification-element-assl.md)|Contains information for the [ProactiveCaching](../objects/proactivecaching-element-assl.md) element about a query to execute to determine the progress of incremental processing.|  
|[KeyColumn Element &#40;ASSL&#41;](../objects/keycolumn-element-assl.md)|Contains the definition of a column that is, or is part of, the key for an attribute.|  
|[Kpi Element &#40;ASSL&#41;](../objects/kpi-element-assl.md)|Defines a key performance indicator (KPI) within a [Cube](../objects/cube-element-assl.md) element or a [Perspective](../objects/perspective-element-assl.md) element.|  
|[Level Element &#40;ASSL&#41;](../objects/level-element-assl.md)|Defines a level in a [Hierarchy](../objects/hierarchy-element-assl.md) element.|  
|[MdxScript Element &#40;ASSL&#41;](../objects/mdxscript-element-assl.md)|Contains information about a Multidimensional Expressions (MDX) script that is associated with a [Cube](../objects/cube-element-assl.md) element.|  
|[Measure Element &#40;ASSL&#41;](../objects/measure-element-assl.md)|Defines a measure.|  
|[MeasureGroup Element &#40;ASSL&#41;](../objects/measuregroup-element-assl.md)|Defines a set of measures at the same level of granularity.|  
|[Member Element &#40;ASSL&#41;](../objects/member-element-assl.md)|Contains the name of a member of a [Group](../objects/group-element-assl.md) element or of a [Role](../objects/role-element-assl.md) element.|  
|[MiningModel Element &#40;ASSL&#41;](../objects/miningmodel-element-assl.md)|Defines a single data mining model.|  
|[MiningModelPermission Element &#40;ASSL&#41;](../objects/miningmodelpermission-element-assl.md)|Defines the permissions members of a [Role](../objects/role-element-assl.md) element have on an individual [MiningModel](../objects/miningmodel-element-assl.md) element.|  
|[MiningStructure Element &#40;ASSL&#41;](../objects/miningstructure-element-assl.md)|Defines the structure for a set of mining models.|  
|[MiningStructurePermission Element &#40;ASSL&#41;](../objects/miningstructurepermission-element-assl.md)|Defines the permissions that members of a [Role](../objects/role-element-assl.md) element have on an individual [MiningStructure](../objects/miningstructure-element-assl.md) element.|  
|[ModelingFlag Element &#40;ASSL&#41;](../objects/modelingflag-element-assl.md)|Contains a modeling flag for a column in a mining structure or a mining model.|  
|[NameColumn Element &#40;ASSL&#41;](../objects/namecolumn-element-assl.md)|Identifies the column that provides the name of the parent element.|  
|[NamingTemplateTranslation Element &#40;ASSL&#41;](../objects/namingtemplatetranslation-element-assl.md)|Provides a localized translation of the **NamingTemplate** element for a parent [DimensionAttribute](data-type/dimensionattribute-data-type-assl.md) data type.|  
|[Partition Element &#40;ASSL&#41;](../objects/partition-element-assl.md)|Defines a partition of a [MeasureGroup](../objects/measuregroup-element-assl.md) element or a partition binding in an out-of-line [MeasureGroupBinding](data-type/measuregroupbinding-data-type-out-of-line-assl.md)element.|  
|[Perspective Element &#40;ASSL&#41;](../objects/perspective-element-assl.md)|Defines details for a perspective of a [Cube](../objects/cube-element-assl.md) element.|  
|[ProactiveCaching Element &#40;ASSL&#41;](../objects/proactivecaching-element-assl.md)|Defines proactive caching settings for the parent element.|  
|[QueryNotification Element &#40;ASSL&#41;](../objects/querynotification-element-assl.md)|Contains information for the [ProactiveCaching](../objects/proactivecaching-element-assl.md) element about a query to execute to determine whether a data source has been modified.|  
|[ReportFormatParameter Element &#40;ASSL&#41;](../objects/reportformatparameter-element-asl.md)|Contains the name and value of a parameter that specifies how a  Reporting Service report is formatted at run time.|  
|[ReportParameter Element &#40;ASSL&#41;](../objects/reportparameter-element-assl.md)|Contains the name and value of a parameter that is passed to a Reporting Service report at run time.|  
|[Role Element &#40;ASSL&#41;](../objects/role-element-assl.md)|Contains information about a security role.|  
|[Server Element &#40;ASSL&#41;](../objects/server-element-assl.md)|Describes an instance ofAnalysis Services.|  
|[ServerProperty Element &#40;ASSL&#41;](../objects/serverproperty-element-assl.md)|Defines a server property associated with a [Server](../objects/server-element-assl.md) element.|  
|[SkippedLevelsColumn Element &#40;ASSL&#41;](../objects/skippedlevelscolumn-element-assl.md)|Provides the details of a column that stores the number of skipped (empty) levels between each member and its parent.|  
|[SourceMeasureGroup Element &#40;ASSL&#41;](../objects/sourcemeasuregroup-element-assl.md)|Identifies the measure group that serves as the data source for a mining structure column.|  
|[TableNotification Element &#40;ASSL&#41;](../objects/tablenotification-element-assl.md)|Contains information for the [ProactiveCaching](../objects/proactivecaching-element-assl.md) element about a table or view in a data source that has been modified.|  
|[Trace Element &#40;ASSL&#41;](../objects/trace-element-assl.md)|Defines a trace that can be queried.|  
|[Translation Element &#40;ASSL&#41;](../objects/translation-element-assl.md)|Provides a localized translation for the parent of the [Translations](../collections/translations-element-assl.md) collection.|  
|[UnaryOperatorColumn Element &#40;ASSL&#41;](../objects/unaryoperatorcolumn-element-assl.md)|Defines the details of a column providing a unary operator.|  
|[UnknownMemberTranslation Element &#40;ASSL&#41;](../objects/unknownmembertranslation-element-assl.md)|Contains a translation for the caption of the [UnknownMember](../properties/unknownmember-element-assl.md) element for a [Dimension](../objects/dimension-element-assl.md) element.|  
|[ValueColumn Element &#40;ASSL&#41;](../objects/valuecolumn-element-assl.md)|Identifies the column that provides the value of the parent element.|  
  
## See Also  
 [Analysis Services Scripting Language XML Element Hierarchy &#40;ASSL&#41;](analysis-services-scripting-language-xml-element-hierarchy-assl.md)  
  
  

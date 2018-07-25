---
title: "Binding Data Type (ASSL) | Microsoft Docs"
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
# Binding Data Type (ASSL)

  Defines an abstract primitive data type that represents a dependent relationship between two objects in which the data or metadata of one object is dependent on the data or metadata of a bound object.  
  
## Syntax  
  
```xml  
  
<Binding>...</Binding>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|None|  
|Derived data types|[AttributeBinding](data-type/attributebinding-data-type-assl.md), [ColumnBinding](data-type/columnbinding-data-type-assl.md), [CubeAttributeBinding](data-type/cubeattributebinding-data-type-assl.md), [CubeDimensionBinding](data-type/cubedimensionbinding-data-type-assl.md), [DataSourceViewBinding](data-type/datasourceviewbinding-data-type-assl.md), [DimensionBinding](data-type/dimensionbinding-data-type-assl.md), [InheritedBinding](data-type/inheritedbinding-data-type-assl.md), [MeasureBinding](data-type/measurebinding-data-type-assl.md), [MeasureGroupBinding](data-type/measuregroupbinding-data-type-assl.md), [MeasureGroupDimensionBinding](data-type/measuregroupdimensionbinding-data-type-assl.md), [ProactiveCachingBinding](data-type/proactivecachingbinding-data-type-assl.md), [RowBinding](data-type/rowbinding-data-type-assl.md), [TabularBinding](data-type/tabularbinding-data-type-assl.md), [TimeAttributeBinding](data-type/timeattributebinding-data-type-assl.md), [TimeBinding](data-type/timebinding-data-type-assl.md), [UserDefinedGroupBinding](data-type/userdefinedgroupbinding-data-type-assl.md)|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|None|  
|Derived elements|None|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Binding>.  
  
 For more information about data binding, see [Data Sources and Bindings &#40;SSAS Multidimensional&#41;](../../../analysis-services/multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).  
  
## Elements of Type Binding  
 The following table lists elements of type **Binding**.  
  
|Parent Element|Element of type **Binding**|Comments|  
|--------------------|---------------------------------|--------------|  
|[AttributeTranslation](data-type/attributetranslation-data-type-assl.md)|[Source](properties/source-element-binding-assl.md) of [CaptionColumn](objects/captioncolumn-element-assl.md) (of type [DataItem](data-type/dataitem-data-type-assl.md))|Type of the **Binding** must be [AttributeBinding](data-type/attributebinding-data-type-assl.md) or [ColumnBinding](data-type/columnbinding-data-type-assl.md)|  
|[Cube](objects/cube-element-assl.md)|[Source](properties/source-element-binding-assl.md)|Type of the **Binding** must be [DataSourceViewBinding](data-type/datasourceviewbinding-data-type-assl.md)|  
|[CubeBinding (out-of-line)](data-type/cubebinding-data-type-out-of-line-assl.md)|[MeasureGroup](objects/measuregroup-element-assl.md)|Type of the **Binding** must be [MeasureGroupBinding](data-type/measuregroupbinding-data-type-assl.md)|  
|[DataItem](data-type/dataitem-data-type-assl.md)|[Source](properties/source-element-binding-assl.md)|**Binding** may be of any type|  
|[Dimension](objects/dimension-element-assl.md)|[Source](properties/source-element-binding-assl.md)|Type of the **Binding** must be [CubeDimensionBinding](data-type/cubedimensionbinding-data-type-assl.md), [DataSourceViewBinding](data-type/datasourceviewbinding-data-type-assl.md), [DimensionBinding](data-type/dimensionbinding-data-type-assl.md), or [TimeBinding](data-type/timebinding-data-type-assl.md)|  
|[DimensionAttribute](data-type/dimensionattribute-data-type-assl.md)|[Source](properties/source-element-binding-assl.md)|Type of the **Binding** must be [AttributeBinding](data-type/attributebinding-data-type-assl.md) or [UserDefinedGroupBinding](data-type/userdefinedgroupbinding-data-type-assl.md)|  
|[DrillThroughAction](data-type/drillthroughaction-data-type-assl.md)|[Column](objects/column-element-assl.md)|Type of the **Binding** must be [CubeAttributeBinding](data-type/cubeattributebinding-data-type-assl.md) or [MeasureBinding](data-type/measurebinding-data-type-assl.md)|  
|[Measure](objects/measure-element-assl.md)|[Source](properties/source-element-binding-assl.md) (of type [DataItem](data-type/dataitem-data-type-assl.md))|Type of the **Binding** must be [ColumnBinding](data-type/columnbinding-data-type-assl.md), [CubeDimensionBinding](data-type/cubedimensionbinding-data-type-assl.md), [MeasureBinding](data-type/measurebinding-data-type-assl.md), or [RowBinding](data-type/rowbinding-data-type-assl.md)|  
|[MeasureGroup](objects/measuregroup-element-assl.md)|[Source](properties/source-element-binding-assl.md)|Type of the **Binding** must be [MeasureGroupBinding](data-type/measuregroupbinding-data-type-assl.md)|  
|[MeasureGroupAttribute](data-type/measuregroupattribute-data-type-assl.md)|[Source](properties/source-element-binding-assl.md) of [KeyColumn](objects/keycolumn-element-assl.md) (of type [DataItem](data-type/dataitem-data-type-assl.md))|Type of the **Binding** must be [AttributeBinding](data-type/attributebinding-data-type-assl.md) or [ColumnBinding](data-type/columnbinding-data-type-assl.md), or [InheritedBinding](data-type/inheritedbinding-data-type-assl.md)|  
|[MeasureGroupBinding (out-of-line)](data-type/measuregroupbinding-data-type-out-of-line-assl.md)|[Dimension](objects/dimension-element-assl.md)|Type of the **Binding** must be [MeasureGroupDimensionBinding](data-type/measuregroupdimensionbinding-data-type-assl.md)|  
|[MeasureGroupBinding (out-of-line)](data-type/measuregroupbinding-data-type-out-of-line-assl.md)|[Measure](objects/measure-element-assl.md)|Type of the **Binding** must be [MeasureBinding](data-type/measurebinding-data-type-assl.md)|  
|[MeasureGroupBinding (out-of-line)](data-type/measuregroupbinding-data-type-out-of-line-assl.md)|[Partition](objects/partition-element-assl.md)|Type of the **Binding** must be [PartitionBinding](data-type/partitionbinding-data-type-assl.md)|  
|[MeasureGroupBinding (out-of-line)](data-type/measuregroupbinding-data-type-out-of-line-assl.md)|[Source](properties/source-element-binding-assl.md)|Type of the **Binding** must be [TableBinding](data-type/tablebinding-data-type-assl.md)|  
|[MeasureGroupDimension](data-type/measuregroupdimension-data-type-assl.md)|[Source](properties/source-element-binding-assl.md)|Type of the **Binding** must be [MeasureGroupDimensionBinding](data-type/measuregroupdimensionbinding-data-type-assl.md)|  
|[MiningStructure](objects/miningstructure-element-assl.md)|[Source](properties/source-element-binding-assl.md)|Type of the **Binding** must be [CubeDimensionBinding](data-type/cubedimensionbinding-data-type-assl.md), [DataSourceViewBinding](data-type/datasourceviewbinding-data-type-assl.md), or [DimensionBinding](data-type/dimensionbinding-data-type-assl.md)|  
|[Partition](objects/partition-element-assl.md)|[Source](properties/source-element-binding-assl.md)|Type of the **Binding** must be [TabularBinding](data-type/tabularbinding-data-type-assl.md)|  
|[ProactiveCaching](objects/proactivecaching-element-assl.md)|[Source](properties/source-element-binding-assl.md)|Type of the **Binding** must be [ProactiveCachingBinding](data-type/proactivecachingbinding-data-type-assl.md)|  
|[ScalarMiningStructureColumn](data-type/scalarminingstructurecolumn-data-type-assl.md)|[Source](properties/source-element-binding-assl.md)|Type of the **Binding** must be [AttributeBinding](data-type/attributebinding-data-type-assl.md), [CubeAttributeBinding Data Type &#40;ASSL&#41;](data-type/cubeattributebinding-data-type-assl.md), or [MeasureBinding Data Type &#40;ASSL&#41;](data-type/measurebinding-data-type-assl.md)|  
|[TableMiningStructureColumn](data-type/tableminingstructurecolumn-data-type-assl.md)|[SourceMeasureGroup](objects/sourcemeasuregroup-element-assl.md)|Type of the **Binding** must be [MeasureGroupBinding](data-type/measuregroupbinding-data-type-assl.md)|  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](data-type/analysis-services-scripting-language-xml-data-types-assl.md)  
  
  

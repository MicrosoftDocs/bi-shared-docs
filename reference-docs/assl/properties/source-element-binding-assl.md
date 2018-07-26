---
title: "Source Element (Binding) (ASSL) | Microsoft Docs"
ms.date: 7/25/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
---
# Source Element (Binding) (ASSL)

  Identifies the source of data to which the parent element is bound.  
  
## Syntax  
  
```xml  
  
<AggregationInstance> <!-- or one of the elements listed below in the Element Relationships table -->  
   ...  
   <Source>...</Source>  
   ...  
</Cube>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|See the table below.|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
|Ancestor or Parent|Data Type|  
|------------------------|---------------|  
|[AggregationInstance](../objects/aggregationinstance-element-assl.md)|[TabularBinding](../data-type/tabularbinding-data-type-assl.md)|  
|[AggregationInstanceMeasure](../data-type/aggregationinstancemeasure-data-type-assl.md)|[ColumnBinding](../data-type/columnbinding-data-type-assl.md)|  
|[Cube](../objects/cube-element-assl.md)|[DataSourceViewBinding](../data-type/datasourceviewbinding-data-type-assl.md)|  
|[DataItem](../data-type/dataitem-data-type-assl.md)|Any data type derived from [Binding](../data-type/binding-data-type-assl.md), depending on the parent of **DataItem**. For more information, see Remarks.|  
|[Dimension](../objects/dimension-element-assl.md)|[CubeDimensionBinding](../data-type/cubedimensionbinding-data-type-assl.md), [DataSourceViewBinding](../data-type/datasourceviewbinding-data-type-assl.md), [DimensionBinding](../data-type/dimensionbinding-data-type-assl.md), [TimeBinding](../data-type/timebinding-data-type-assl.md)|  
|[DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md)|[AttributeBinding](../data-type/attributebinding-data-type-assl.md), [UserDefinedGroupBinding](../data-type/userdefinedgroupbinding-data-type-assl.md)|  
|[MeasureGroup](../objects/measuregroup-element-assl.md)|[MeasureGroupBinding](../data-type/measuregroupbinding-data-type-assl.md)|  
|[MeasureGroupDimension](../data-type/measuregroupdimension-data-type-assl.md)|[MeasureGroupDimensionBinding](../data-type/measuregroupdimensionbinding-data-type-assl.md)|  
|[MiningStructure](../objects/miningstructure-element-assl.md)|[CubeDimensionBinding](../data-type/cubedimensionbinding-data-type-assl.md), [DataSourceViewBinding](../data-type/datasourceviewbinding-data-type-assl.md), [DimensionBinding](../data-type/dimensionbinding-data-type-assl.md)|  
|[Partition](../objects/partition-element-assl.md)|[TabularBinding](../data-type/tabularbinding-data-type-assl.md)|  
|[ProactiveCaching](../objects/proactivecaching-element-assl.md)|Any data type derived from [ProactiveCachingBinding](../data-type/proactivecachingbinding-data-type-assl.md), depending on the processing and notification options used by the parent of the **ProactiveCaching** element.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[AggregationInstance](../objects/aggregationinstance-element-assl.md), [AggregationInstanceMeasure](../data-type/aggregationinstancemeasure-data-type-assl.md), [Cube](../objects/cube-element-assl.md), [DataItem](../data-type/dataitem-data-type-assl.md), [Dimension](../objects/dimension-element-assl.md), [DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md), [MeasureGroup](../objects/measuregroup-element-assl.md), [MeasureGroupDimension](../data-type/measuregroupdimension-data-type-assl.md), [MiningStructure](../objects/miningstructure-element-assl.md), [Partition](../objects/partition-element-assl.md), [ProactiveCaching](../objects/proactivecaching-element-assl.md).|  
|Child elements|None|  
  
## Remarks  
 In the **Source** element, the derived **Binding** data types that are allowed in the **DataItem** element depend on the parent of the **DataItem** element.  
  
|DataItem Parent|Allowed Data Types|  
|---------------------|------------------------|  
|[DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md)|[AttributeBinding](../data-type/attributebinding-data-type-assl.md), [ColumnBinding](../data-type/columnbinding-data-type-assl.md), [TimeAttributeBinding](../data-type/timeattributebinding-data-type-assl.md) (only for [KeyColumns](../collections/keycolumns-element-assl.md)).|  
|[MeasureGroupAttribute](../data-type/measuregroupattribute-data-type-assl.md)|[AttributeBinding](../data-type/attributebinding-data-type-assl.md), [ColumnBinding](../data-type/columnbinding-data-type-assl.md), [InheritedBinding](../data-type/inheritedbinding-data-type-assl.md).|  
|[ScalarMiningStructureColumn](../data-type/scalarminingstructurecolumn-data-type-assl.md)|[ColumnBinding](../data-type/columnbinding-data-type-assl.md)|  
  
 For more information about the **Binding** type, including tables of Analysis Services Scripting Language (ASSL) objects of the **Binding** type and the inheritance hierarchy of **Binding** types, see [Binding Data Type &#40;ASSL&#41;](../data-type/binding-data-type-assl.md).  
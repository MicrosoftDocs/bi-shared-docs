---
title: "MeasureGroup Element (ASSL) | Microsoft Docs"
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
# MeasureGroup Element (ASSL)

  Defines a set of measures at the same level of granularity.  
  
## Syntax  
  
```xml  
  
<MeasureGroups>  
   <MeasureGroup> <!-- ancestor: Cube -->  
      <Name>...</Name>  
      <ID>...</ID>  
      <CreatedTimestamp>...</<Create  
      <LastSchemaUpdate>...</LastSchemaUpdate>  
      <Description>...</Description>  
      <LastProcessed>...</LastProcessed>  
      <Translations>...</Translations>  
      <Type>...</Type>  
      <State>...</State>  
      <MeasureQualification>...</MeasureQualification>  
      <Measures>...</Measures>  
      <DataAggregation>...</DataAggregation>  
      <Source>...</Source>  
            <StorageMode>...</StorageMode>  
      <StorageLocation>...</StorageLocation>  
      <IgnoreUnrelatedDimensions>...</IgnoreUnrelatedDimensions>  
            <ProactiveCaching>...</ProactiveCaching>  
      <EstimatedRows>...</EstimatedRows>  
      <ErrorConfiguration>...</ErrorConfiguration>  
      <EstimatedSize>...</EstimatedSize>  
      <ProcessingMode>...</ProcessingMode>  
      <Dimensions>...</Dimensions>  
      <Partitions>...</Partitions>  
      <AggregationPrefix>...</AggregationPrefix>  
      <ProcessingPriority>...</ProcessingPriority>  
            <AggregationDesigns>...</AggregationDesigns>  
      <Annotations>...</Annotations>  
   </MeasureGroup>  
   <!-- or  -->  
   <MeasureGroup xsi:type="MeasureGroupBinding">...</MeasureGroup> <!-- ancestor: CubeBinding -->  
   <!-- or  -->  
   <MeasureGroup xsi:type="PerspectiveMeasureGroup">...</MeasureGroup> <!-- ancestor: Perspective -->  
</MeasureGroups>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|See the table below.|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
|Ancestor or Parent|Data Type|  
|------------------------|---------------|  
|[Cube](cube-element-assl.md)|None|  
|[CubeBinding](../data-type/cubebinding-data-type-out-of-line-assl.md)|[MeasureGroupBinding](../data-type/measuregroupbinding-data-type-assl.md)|  
|[Perspective](perspective-element-assl.md)|[PerspectiveMeasureGroup](../data-type/perspectivemeasuregroup-data-type-assl.md)|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[MeasureGroups](../collections/measuregroups-element-assl.md)|  
|Child elements|See the table below.|  
  
|Ancestor or Parent|Child elements|  
|------------------------|--------------------|  
|[Cube](cube-element-assl.md)|[AggregationDesigns](../collections/aggregationdesigns-element-assl.md), [AggregationPrefix](../properties/aggregationprefix-element-assl.md), [Annotations](../collections/annotations-element-assl.md), [CreatedTimestamp](../properties/createdtimestamp-element-assl.md), [DataAggregation](../properties/dataaggregation-element-assl.md), [Description](../properties/description-element-assl.md), [Dimensions](../collections/dimensions-element-assl.md), [ErrorConfiguration](errorconfiguration-element-assl.md), [EstimatedRows](../properties/estimatedrows-element-assl.md), [EstimatedSize](../properties/estimatedsize-element-assl.md), [ID](../properties/id-element-assl.md), [IgnoreUnrelatedDimensions](../properties/ignoreunrelateddimensions-element-assl.md), [LastProcessed](../properties/lastprocessed-element-assl.md), [LastSchemaUpdate](../properties/lastschemaupdate-element-assl.md), [MeasureQualification](../properties/measurequalificaton-element-assl.md), [Measures](../collections/measures-element-assl.md), [Name](../properties/name-element-assl.md), [Partitions](../collections/partitions-element-assl.md), [ProactiveCaching](proactivecaching-element-assl.md), [ProcessingMode](../properties/processingmode-element-assl.md), [ProcessingPriority](../properties/processingpriority-element-assl.md), [Source](../properties/source-element-measure-assl.md), [State](../properties/state-element-assl.md), [StorageLocation](../properties/storagelocation-element-assl.md), [StorageMode](../properties/storagemode-element-assl.md), [Translations](../collections/translations-element-assl.md), [Type](../properties/type-element-measuregroup-assl.md)|  
|[CubeBinding](../data-type/cubebinding-data-type-out-of-line-assl.md)|None|  
|[Perspective](perspective-element-assl.md)|None|  
  
## Remarks  
 All the measures of a measure group must be sourced from a single table. A measure group can define default bindings that can be overridden for each partition.  
  
 The **MeasureGroup** element defines details common to measure groups on regular cubes and virtual cubes. Separate subtypes define the details specific to each type.  
  
 The **State** property of a **MeasureGroup** has the following values:  
  
-   *FullyProcessed* if all partitions are processed.  
  
-   *PartiallyProcessed* if at least one partition is processed.  
  
-   *Unprocessed* if no partitions are processed.  
  
 The corresponding elements in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.MeasureGroup> and <xref:Microsoft.AnalysisServices.PerspectiveMeasureGroup>.  
  
## See Also  
 [Objects &#40;ASSL&#41;](objects-assl.md)  
  
  

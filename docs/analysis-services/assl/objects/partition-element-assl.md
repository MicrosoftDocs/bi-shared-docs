---
title: "Partition Element (ASSL) | Microsoft Docs"
description: Learn about the Partition object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Partition Element (ASSL)

  Defines a partition of a [MeasureGroup](../objects/measuregroup-element-assl.md) element or a partition binding in an out-of-line [MeasureGroupBinding](../data-type/measuregroupbinding-data-type-out-of-line-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Partitions>  
      <Partition> <!-- ancestor: MeasureGroup -->  
      <Name>...</Name>  
      <ID>...</ID>  
      <CreatedTimestamp>...</CreatedTimestamp>  
      <LastSchemaUpdate>...</LastSchemaUpdate>  
      <Description>...</Description>  
      <Source>...</Source>  
      <ProcessingPriority>...</ProcessingPriority>  
      <AggregationPrefix>...</AggregationPrefix>  
      <StorageMode>...</StorageMode>  
      <ProcessingMode>...</ProcessingMode>  
      <ErrorConfiguration>...</ErrorConfiguration>  
      <StorageLocation>...</StorageLocation>  
      <RemoteDatasourceID>...</RemoteDatasourceID>  
      <Slice>...</Slice>  
      <ProactiveCaching>...</ProactiveCaching>  
      <Type>...</Type>  
      <EstimatedSize>...</EstimatedSize>  
      <EstimatedRows>...</EstimatedRows>  
      <CurrentStorageMode>...</CurrentStorageMode>  
      <AggregationDesignID>...</AggregationDesignID>  
      <AggregationInstances>...</AggregationInstances>  
      <AggregationInstanceSource>...</AggregationInstanceSource>  
      <LastProcessed>...</LastProcessed>  
      <State>...</State>  
      <Annotations>.../Annotations>  
   </Partition>  
   <!-- or -->  
   <Partition xsi:type="PartitionBinding"> <!-- ancestor: MeasureGroupBinding -->  
   </Partition>  
</Partitions>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|See the table below.|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
|Ancestor or Parent|Data Type|  
|------------------------|---------------|  
|[MeasureGroup](../objects/measuregroup-element-assl.md)|None|  
|[MeasureGroupBinding](../data-type/measuregroupbinding-data-type-out-of-line-assl.md)|[PartitionBinding](../data-type/partitionbinding-data-type-assl.md)|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Partitions](../collections/partitions-element-assl.md)|  
|Child elements|See the table below.|  
  
|Ancestor or Parent|Child elements|  
|------------------------|--------------------|  
|[MeasureGroup](../objects/measuregroup-element-assl.md)|[AggregationDesignID](../properties/aggregationdesignid-element-assl.md), [AggregationInstances](../collections/aggregationinstances-element-assl.md), [AggregationInstanceSource](../properties/aggregationinstancesource-element-assl.md), [AggregationPrefix](../properties/aggregationprefix-element-assl.md), [Annotations](../collections/annotations-element-assl.md), [CreatedTimestamp](../properties/createdtimestamp-element-assl.md), [CurrentStorageMode](../properties/currentstoragemode-element-assl.md), [Description](../properties/description-element-assl.md), [ErrorConfiguration](../objects/errorconfiguration-element-assl.md), [EstimatedRows](../properties/estimatedrows-element-assl.md), [EstimatedSize](../properties/estimatedsize-element-assl.md), [ID](../properties/id-element-assl.md), [LastProcessed](../properties/lastprocessed-element-assl.md), [LastSchemaUpdate](../properties/lastschemaupdate-element-assl.md), [Name](../properties/name-element-assl.md), [ProactiveCaching](../objects/proactivecaching-element-assl.md), [ProcessingMode](../properties/processingmode-element-assl.md), [ProcessingPriority](../properties/processingpriority-element-assl.md), [RemoteDatasourceID](../properties/remotedatasourceid-element-assl.md), [Slice](../properties/slice-element-assl.md), [Source](../properties/source-element-binding-assl.md), [State](../properties/state-element-assl.md), [StorageLocation](../properties/storagelocation-element-assl.md), [StorageMode](../properties/storagemode-element-assl.md), [Type](../properties/type-element-partition-assl.md)|  
|[MeasureGroupBinding](../data-type/measuregroupbinding-data-type-out-of-line-assl.md)|None|  
  
## Remarks  
 This element has the following validations under DeploymentMode value 2 (tabular server mode):  
  
-   The following children elements are not supported and should not be used:  
  
    -   [ProcessingPriority](../properties/processingpriority-element-assl.md)  
  
    -   [AggregationPrefix](../properties/aggregationprefix-element-assl.md)  
  
    -   [StorageLocation](../properties/storagelocation-element-assl.md)  
  
    -   [ProcessingMode](../properties/processingmode-element-assl.md)  
  
    -   [ErrorConfiguration](../objects/errorconfiguration-element-assl.md)  
  
    -   [StorageLocation](../properties/storagelocation-element-assl.md)  
  
    -   [RemoteDatasourceID](../properties/remotedatasourceid-element-assl.md)  
  
    -   [Slice](../properties/slice-element-assl.md)  
  
    -   [ProactiveCaching](../objects/proactivecaching-element-assl.md)  
  
    -   [Type](../properties/type-element-partition-assl.md)  
  
    -   [CurrentStorageMode](../properties/currentstoragemode-element-assl.md)  
  
    -   [AggregationDesignID](../properties/aggregationdesignid-element-assl.md)  
  
    -   [AggregationInstances](../collections/aggregationinstances-element-assl.md)  
  
    -   [AggregationInstanceSource](../properties/aggregationinstancesource-element-assl.md)  
  
     An error might be thrown if any of the above elements is used.  
  
-   The [Source](../properties/source-element-binding-assl.md) element only accepts **Query** binding.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Partition>.  
  
## See Also  
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

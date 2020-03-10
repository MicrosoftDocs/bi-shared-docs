---
title: "Target Element (XMLA) | Microsoft Docs"
ms.date: 07/24/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Target Element (XMLA)

  Represents the target partition to be merged during a [MergePartitions](../xml-elements-commands/mergepartitions-element-xmla.md) command.  
  
## Syntax  
  
```xml  
  
<MergePartitions>  
   <Target>  
      <DatabaseID>...</DatabaseID>  
      <CubeID>...</CubeID>  
      <MeasureGroupID>...</MeasureGroupID>  
      <PartitionID>...</PartitionID>  
   </Target>  
</MergePartitions>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|1-n: Required element that can occur more than once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[MergePartitions](../xml-elements-commands/mergepartitions-element-xmla.md)|  
|Child elements|[CubeID](../xml-elements-properties/cubeid-element-xmla.md), [DatabaseID](../xml-elements-properties/databaseid-element-xmla.md), [MeasureGroupID](../xml-elements-properties/measuregroupid-element-xmla.md), [PartitionID](../xml-elements-properties/partitionid-element-xmla.md)|  
  
## Remarks  
 The **Target** element is an object reference to a single partition into which the contents of the source partitions, specified by the [Sources](../xml-elements-properties/sources-element-xmla.md) element of the parent **MergePartitions** element, are to be merged.  
  
## Example  
 The following example combines all four partitions of the Internet Sales measure group into the `Internet_Sales_2004` target partition. The example refers to the cube of the sample database.  
  
```xml  
<MergePartitions xmlns="http://schemas.microsoft.com/analysisservices/2003/engine">  
  <Sources>  
     <Source>  
        <DatabaseID>database</DatabaseID>  
        <CubeID>Adventure Works DW</CubeID>  
        <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
        <PartitionID>Internet_Sales_2001</PartitionID>  
     </Source>  
     <Source>  
      <DatabaseID>database</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2002</PartitionID>  
    </Source>  
    <Source>  
      <DatabaseID>database</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2003</PartitionID>  
    </Source>  
  </Sources>  
  <Target>    <DatabaseID>database</DatabaseID>    <CubeID>Adventure Works DW</CubeID>    <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>    <PartitionID>Internet_Sales_2004</PartitionID>  </Target>  
</MergePartitions>  
```  

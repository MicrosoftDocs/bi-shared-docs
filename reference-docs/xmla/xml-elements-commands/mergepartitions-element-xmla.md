---
title: "MergePartitions Element (XMLA) | Microsoft Docs"
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
# MergePartitions Element (XMLA)

  Merges the data of one or more source partitions into a target partition, and then deletes the source partitions.  
  
## Syntax  
  
```xml  
  
<Command>  
   <MergePartitions>  
      <Sources>...</Sources>  
      <Target>...</Target>  
   </MergePartitions>  
</Command>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Command](../xml-elements-properties/command-element-xmla.md)|  
|Child elements|[Sources](../xml-elements-properties/sources-element-xmla.md), [Target](../xml-elements-properties/target-element-xmla.md)|  
  
## Remarks  
 All object references in the **Sources** and **Target** elements must point to distinct partitions in the same measure group. Otherwise, an error occurs.  
---
title: "MeasureGroupAttributeBinding Data Type (out-of-line) (ASSL) | Microsoft Docs"
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
# MeasureGroupAttributeBinding Data Type (out-of-line) (ASSL)

  Defines a derived data type that represents an out-of-line binding for an attribute in a dimension included in a measure group.  
  
## Syntax  
  
```xml  
  
<MeasureGroupAttributeBinding>  
   <!-- The following elements extend Binding -->  
   <DatabaseID>...</DatabaseID>  
   <CubeID>...</CubeID>  
   <MeasureGroupID>...</MeasureGroupID>  
   <GranularityAttributeID>...</GranularityAttributeID>  
   <Source>...</Source>  
</MeasureGroupAttributeBinding>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[Binding](binding-data-type-assl.md)|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[CubeID](../properties/cubeid-element-assl.md), [DatabaseID](../../xmla/xml-elements-../properties/databaseid-element-xmla.md), [MeasureGroupID](../properties/measuregroupid-element-assl.md), [GranularityAttributeID](../properties/granularityattributeid-element-assl.md), [Source](../properties/source-element-binding-assl.md)|  
|Derived elements|[Binding](../../xmla/xml-elements-../properties/binding-element-xmla.md) ([Bindings](../collections/attributes-element-assl.md) collection of XML for Analysis (XMLA) [Batch](../../xmla/xml-elements-commands/batch-element-xmla.md) and [Process](../../xmla/xml-elements-commands/process-element-xmla.md) commands)|  
  
## Remarks  

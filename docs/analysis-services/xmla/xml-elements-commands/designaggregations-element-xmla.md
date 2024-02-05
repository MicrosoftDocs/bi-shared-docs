---
title: "DesignAggregations Element (XMLA) | Microsoft Docs"
description: Learn how the DesignAggregations element creates aggregations for an aggregation design on a Analysis Services instance.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# DesignAggregations Element (XMLA)

  Creates aggregations for an aggregation design on a Analysis Services instance.  
  
## Syntax  
  
```xml  
  
<Command>  
   <DesignAggregations>  
      <Object>...</Object>  
      <Time>...</Time>  
      <Steps>...</Steps>  
      <Optimization>...</Optimization>  
      <Storage>...</Storage>  
      <Materialize>...</Materialize>  
      <Queries>...</Queries>  
   </DesignAggregations>  
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
|Child elements|[Materialize](../xml-elements-properties/materialize-element-xmla.md), [Object](../xml-elements-properties/object-element-xmla.md), [Optimization](../xml-elements-properties/optimization-element-xmla.md), [Queries](../xml-elements-properties/queries-element-xmla.md), [Steps](../xml-elements-properties/steps-element-xmla.md), [Storage](../xml-elements-properties/storage-element-xmla.md), [Time](../xml-elements-properties/time-element-xmla.md)|  
  
## Remarks  
 The **DesignAggregations** command is used to generate aggregation definitions stored by an aggregation design. An aggregation design can then be used to materialize aggregations for a partition and can be reused between partitions.  
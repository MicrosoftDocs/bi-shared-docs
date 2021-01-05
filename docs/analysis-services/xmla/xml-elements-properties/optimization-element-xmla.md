---
title: "Optimization Element (XMLA) | Microsoft Docs"
description: Learn how the Optimization element specifies the optimization threshold percentage used by the DesignAggregations command to design aggregations.
ms.date: 01/05/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Optimization Element (XMLA)

  Specifies the optimization threshold percentage used by the [DesignAggregations](../xml-elements-commands/designaggregations-element-xmla.md) command to design aggregations.  
  
## Syntax  
  
```xml  
  
<DesignAggregations>  
   ...  
   <Optimization>...</Optimization>  
   ...  
</DesignAggregations>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Double|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[DesignAggregations](../xml-elements-commands/designaggregations-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  

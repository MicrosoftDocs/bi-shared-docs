---
title: "Materialize Element (XMLA) | Microsoft Docs"
description: Learn how the Materialize element specifies whether to materialize the aggregations designed by the DesignAggregations command. 
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Materialize Element (XMLA)

  Specifies whether to materialize the aggregations designed by the [DesignAggregations](../xml-elements-commands/designaggregations-element-xmla.md) command.  
  
## Syntax  
  
```xml  
  
<DesignAggregations>  
   ...  
   <Materialize>...</Materialize>  
   ...  
</DesignAggregations>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Boolean|  
|Default value|False|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[DesignAggregations](../xml-elements-commands/designaggregations-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  

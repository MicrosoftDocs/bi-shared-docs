---
title: "Queries Element (XMLA) | Microsoft Docs"
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
# Queries Element (XMLA)

  Contains a collection of [Query](../xml-elements-properties/query-element-xmla.md) elements used by the [DesignAggregations](../xml-elements-commands/designaggregations-element-xmla.md) command during usage-based optimization.  
  
## Syntax  
  
```xml  
  
<DesignAggregations>  
   ...  
   <Queries>  
      <Query>...</Query>  
   </Queries>  
   ...  
</DesignAggregations>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[DesignAggregations](../xml-elements-commands/designaggregations-element-xmla.md)|  
|Child elements|[Query](../xml-elements-properties/query-element-xmla.md)|  
  
## Remarks  
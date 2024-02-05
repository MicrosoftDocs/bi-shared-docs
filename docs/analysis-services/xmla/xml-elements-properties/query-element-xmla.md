---
title: "Query Element (XMLA) | Microsoft Docs"
description: Learn how the Query element contains a query within the Queries collection used by the DesignAggregations command during usage-based optimization.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Query Element (XMLA)

  Contains a query within the [Queries](../xml-elements-properties/queries-element-xmla.md) collection used by the [DesignAggregations](../xml-elements-commands/designaggregations-element-xmla.md) command during usage-based optimization.  
  
## Syntax  
  
```xml  
  
<Queries>  
   ...  
   <Query>...</Query>  
   ...  
</Queries>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Queries](../xml-elements-properties/queries-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **DesignAggregations** command supports usage-based optimization by including one or more **Query** elements in the **Queries** collection of the command. Each **Query** element represents a goal query that the design process uses to define aggregations that target the most frequently used queries. You can either specify your own goal queries, or you can use the information stored by an instance of Analysis Services in the query log to retrieve information about the most frequently used queries.  
  
 If you are iteratively designing aggregations, you only have to pass goal queries in the first **DesignAggregations** command because the instance stores these goal queries and uses these queries during subsequent **DesignAggregations** commands. After you pass goal queries in the first **DesignAggregations** command of an iterative process, any subsequent **DesignAggregations** command that contains goal queries in the **Queries** property generates an error.  
  
 The **Query** element contains a comma-delimited value that contains the following arguments:  
  
 *Frequency*,*Dataset*[,*Dataset*...]  
  
 *Frequency*  
 A weighting factor that corresponds to the number of times that the query has previously been executed. If the **Query** element represents a new query, the *Frequency* value represents the weighting factor used by the design process to evaluate the query. As the frequency value becomes larger, the weight that is put on the query during the design process increases.  
  
 *Dataset*  
 A numeric string that specifies which attributes from a dimension are to be included in the query. This string must have the same number of characters as the number of attributes in the dimension. Zero (0) indicates that the attribute in the specified ordinal position is not included in the query for the specified dimension, while one (1) indicates that the attribute in the specified ordinal position is included in the query for the specified dimension.  
  
 For example, the string "011" would refer to a query involving a dimension with three attributes, from which the second and third attributes are included in the query.  
  
> [!NOTE]  
>  Some attributes are excluded from consideration in the dataset.  
  
 Each dimension in the measure group that contains the aggregation design is represented by a *Dataset* value in the **Query** element. The order of *Dataset* values must match the order of dimensions included in the measure group.  


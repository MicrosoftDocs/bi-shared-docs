---
title: "AggregationPrefix Element (ASSL) | Microsoft Docs"
description: Learn about the AggregationPrefix property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference

---
# AggregationPrefix Element (ASSL)

  Defines the common prefix to be used for aggregation names throughout the associated parent element.  
  
## Syntax  
  
```xml  
  
<Cube> <!-- or Database, MeasureGroup, Partition -->  
   ...  
   <AggregationPrefix>...</AggregationPrefix>  
   ...  
</Database>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Cube](../objects/cube-element-assl.md), [Database](../objects/database-element-assl.md), [MeasureGroup](../objects/measuregroup-element-assl.md), [Partition](../objects/partition-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 Aggregation prefixes generate aggregation names in Analysis Services, and also generate table names in the relational database for aggregations stored in a relational OLAP (ROLAP) partition.  
  
 A fully expanded aggregation name has the following parts:  
  
 *\<DatabasePrefix>\<CubePrefix>\<MeasureGroupPrefix>\<PartitionPrefix>\<AggregationID>*  
  
 The first four parts of the aggregation name make up the aggregation prefix. The user provides the first four parts:  
  
-   *DatabasePrefix* represents the value of the **AggregationPrefix** element associated with a **Database** element.  
  
-   *CubePrefix* represents the value of the **AggregationPrefix** element associated with a **Cube** element.  
  
-   *MeasureGroupPrefix* represents the value of the **AggregationPrefix** element associated with a **MeasureGroup** element.  
  
-   *PartitionPrefix* represents the value of the **AggregationPrefix** element associated with a **Partition** element.  
  
 The fifth part of the name, *AggregationID*, is a system-defined ID, and users have no control over this part of the name.  
  
 The elements that correspond to the parents of **AggregationPrefix** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.Cube>, <xref:Microsoft.AnalysisServices.Database>, <xref:Microsoft.AnalysisServices.MeasureGroup>, and <xref:Microsoft.AnalysisServices.Partition>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

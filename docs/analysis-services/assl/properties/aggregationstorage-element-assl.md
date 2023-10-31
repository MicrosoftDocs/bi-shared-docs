---
title: "AggregationStorage Element (ASSL) | Microsoft Docs"
description: Learn about the AggregationStorage property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# AggregationStorage Element (ASSL)

  Identifies the storage method for aggregations.  
  
## Syntax  
  
```xml  
  
<ProactiveCaching>  
   ...  
   <AggregationStorage>...</AggregationStorage>  
   ...  
</ProactiveCaching>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Regular*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[ProactiveCaching](../objects/proactivecaching-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the following strings:  
  
|Value|Description|  
|-----------|-----------------|  
|*Regular*|Aggregation data is stored in the default manner.|  
|*MolapOnly*|Aggregation data is stored using multidimensional OLAP (MOLAP) storage only.|  
  
 The *MolapOnly* option is available only for the [Partition](../objects/partition-element-assl.md) element.  
  
 The enumeration that corresponds to the allowed values for **AggregationStorage** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ProactiveCachingAggregationStorage>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

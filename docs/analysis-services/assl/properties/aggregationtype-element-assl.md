---
title: "AggregationType Element (ASSL) | Microsoft Docs"
description: Learn about the AggregationType property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# AggregationType Element (ASSL)

  Defines the type of aggregation stored by the [Partition](../objects/partition-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<AggregationInstance>  
   ...  
   <AggregationType>...</AggregationType>  
   ...  
</AggregationInstance>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|None|  
|Cardinality|1-1: Required element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[AggregationInstance](../objects/aggregationinstance-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*IndexedView*|The aggregation is stored in an indexed view.|  
|*Table*|The aggregation is stored in a table.|  
|*UserDefined*|The aggregation is user-defined.|  
  
 The enumeration that corresponds to the allowed values for **AggregationType** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.AggregationInstance>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

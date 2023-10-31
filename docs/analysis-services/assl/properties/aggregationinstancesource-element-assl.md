---
title: "AggregationInstanceSource Element (ASSL) | Microsoft Docs"
description: Learn about the AggregationInstanceSource property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# AggregationInstanceSource Element (ASSL)

  Identifies the source of data for user-defined aggregation instances bound to a [Partition](../objects/partition-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Partition>  
   ...  
   <AggregationInstanceSource xsi:type="DataSourceViewBinding">...</AggregationInstanceSource>  
   ...  
</Partition>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[DataSourceViewBinding](../data-type/datasourceviewbinding-data-type-assl.md)|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Partition](../objects/partition-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 If this element is missing or set to a blank string, the data source view of the cube that owns the partition is used by default.  
  
 For additional information about the **Binding** type, including tables of Analysis Services Scripting Language (ASSL) objects of the **Binding** type and the inheritance hierarchy of **Binding** types, see [Binding Data Type &#40;ASSL&#41;](../data-type/binding-data-type-assl.md).  
  
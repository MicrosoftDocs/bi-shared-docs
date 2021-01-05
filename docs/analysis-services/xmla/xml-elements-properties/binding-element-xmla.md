---
title: "Binding Element (XMLA) | Microsoft Docs"
description: Learn how the Binding element defines an out-of-line binding for an Analysis Services object, such as an attribute in a dimension, for the Bindings collection of a Batch or Process command.
ms.date: 01/05/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Binding Element (XMLA)

  Defines an out-of-line binding for an Analysis Services object, such as an attribute in a dimension, for the [Bindings](../xml-elements-properties/bindings-element-xmla.md) collection of a [Batch](../xml-elements-commands/batch-element-xmla.md) or [Process](../xml-elements-commands/process-element-xmla.md) command.  
  
## Syntax  
  
```xml  
  
<Bindings>  
   <Binding xsi:type="DimensionAttributeBinding">...</Binding>  
   <!-- or -->  
   <Binding xsi:type="MeasureGroupAttributeBinding">...</Binding>  
   <!-- or -->  
   <Binding xsi:type="PartitionBinding">...</Binding>  
</Bindings>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[DimensionAttributeBinding](../../assl/data-type/dimensionattributebinding-data-type-out-of-line-assl.md), [MeasureGroupAttributeBinding](../../assl/data-type/measuregroupattributebinding-data-type-out-of-line-assl.md), [PartitionBinding](../../assl/data-type/partitionbinding-data-type-assl.md)|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Bindings](../xml-elements-properties/bindings-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 **Binding** elements define out-of-line bindings, other than data sources and data source views, for Analysis Services objects to be processed by a **Batch** or **Process** command. 

  
---
title: "ProcessingPriority Element (ASSL) | Microsoft Docs"
description: Learn about the ProcessingPriority property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: eur

ms.topic: reference
author: eric-urban
ms.author: eur

---
# ProcessingPriority Element (ASSL)

  Determines the processing priority of the parent object during background operations, for example lazy aggregation, indexing, or clustering.  
  
## Syntax  
  
```xml  
  
<Dimension> <!-- or MeasureGroup, Partition -->  
   ...  
   <ProcessingPriority>...</ProcessingPriority>  
   ...  
</Dimension>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Integer|  
|Default value|**0**|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Dimension](../data-type/dimension-data-type-assl.md), [MeasureGroup](../objects/measuregroup-element-assl.md), [Partition](../objects/partition-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The elements that correspond to the parents of **ProcessingPriority** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.Dimension>, <xref:Microsoft.AnalysisServices.MeasureGroup>, and <xref:Microsoft.AnalysisServices.Partition>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

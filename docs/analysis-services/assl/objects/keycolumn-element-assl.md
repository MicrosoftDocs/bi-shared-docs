---
title: "KeyColumn Element (ASSL) | Microsoft Docs"
description: Learn about the KeyColumn object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# KeyColumn Element (ASSL)

  Contains the definition of a column that is, or is part of, the key for an attribute.  
  
## Syntax  
  
```xml  
  
<KeyColumns>  
   <KeyColumn xsi:type="DataItem">...</KeyColumn>  
<KeyColumns>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[DataItem](../data-type/dataitem-data-type-assl.md)|  
|Default value|None|  
|Cardinality|1-n: Required element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[KeyColumns](../collections/keycolumns-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 For more information about the **DataItem** type, including a table of Analysis Services Scripting Language (ASSL) objects and properties of the **DataItem** type, see [DataItem Data Type &#40;ASSL&#41;](../data-type/dataitem-data-type-assl.md).  
  
 The elements that correspond to the parents of the **KeyColumns** collection in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.AggregationInstanceAttribute>, <xref:Microsoft.AnalysisServices.DimensionAttribute>, <xref:Microsoft.AnalysisServices.MeasureGroupAttribute>, and <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn>.  
  
## See Also  
 [AggregationInstanceAttribute Data Type &#40;ASSL&#41;](../data-type/aggregationinstanceattribute-data-type-assl.md)   
 [AggregationInstanceCubeDimension Data Type &#40;ASSL&#41;](../data-type/aggregationinstancecubedimension-data-type-assl.md)   
 [DimensionAttribute Data Type &#40;ASSL&#41;](../data-type/dimensionattribute-data-type-assl.md)   
 [MeasureGroupAttribute Data Type &#40;ASSL&#41;](../data-type/measuregroupattribute-data-type-assl.md)   
 [ScalarMiningStructureColumn Data Type &#40;ASSL&#41;](../data-type/scalarminingstructurecolumn-data-type-assl.md)   
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

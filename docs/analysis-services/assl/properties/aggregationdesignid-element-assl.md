---
title: "AggregationDesignID Element (ASSL) | Microsoft Docs"
description: Learn about the AggregationDesignID property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# AggregationDesignID Element (ASSL)

  Identifies the [AggregationDesign](../objects/aggregationdesign-element-assl.md) element associated with the [Partition](../objects/partition-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Partition>  
      ...  
   <AggregationDesignID>...</AggregationDesignID>  
   ...  
</Partition>  
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
|Parent elements|[Partition](../objects/partition-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **AggregationDesignID** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Partition>. See also <xref:Microsoft.AnalysisServices.AggregationDesign>.  
  
## See Also  
 [AggregationDesign Element &#40;ASSL&#41;](../objects/aggregationdesign-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

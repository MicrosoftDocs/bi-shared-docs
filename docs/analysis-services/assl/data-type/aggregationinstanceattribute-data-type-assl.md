---
title: "AggregationInstanceAttribute Data Type (ASSL) | Microsoft Docs"
description: Learn about the AggregationInstanceAttribute data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference

---
# AggregationInstanceAttribute Data Type (ASSL)

  Defines a primitive data type that represents information about an attribute used by an aggregation instance.  
  
## Syntax  
  
```xml  
  
<AggregationInstanceAttribute>  
   <AttributeID>...</AttributeID>  
   <KeyColumns>...</KeyColumns>  
</AggregationInstanceAttribute>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|None|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[AttributeID](../properties/attributeid-element-assl.md), [KeyColumns](../collections/keycolumns-element-assl.md)|  
|Derived elements|[Attribute](../objects/attribute-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.AggregationInstanceAttribute>.  

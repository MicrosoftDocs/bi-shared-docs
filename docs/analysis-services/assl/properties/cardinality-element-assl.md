---
title: "Cardinality Element (ASSL) | Microsoft Docs"
description: Learn about the Cardinality property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Cardinality Element (ASSL)

  Indicates the cardinality of the relationship described by an [AttributeRelationship](../objects/attributerelationship-element-assl.md) or [RegularMeasureGroupDimension](../data-type/regularmeasuregroupdimension-data-type-assl.md).  
  
## Syntax  
  
```xml  
  
<AttributeRelationship> <!-- or RegularMeasureGroupDimension -->  
   ...  
   <Cardinality>...</Cardinality>  
   ...  
</AttributeRelationship>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Many*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[AttributeRelationship](../objects/attributerelationship-element-assl.md), [RegularMeasureGroupDimension](../data-type/regularmeasuregroupdimension-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Many*|Many-to-one relationship|  
|*One*|One-to-one relationship|  
  
 The enumeration corresponding to the allowed values for **Cardinality** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Cardinality>.
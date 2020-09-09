---
title: "AttributeRelationships Element (ASSL) | Microsoft Docs"
description: Learn about the AttributeRelationships collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 07/25/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# AttributeRelationships Element (ASSL)

  Contains the collection of [AttributeRelationship](../objects/attributerelationship-element-assl.md) elements for the attribute.  
  
## Syntax  
  
```xml  
  
<Attribute xsi:type="DimensionAttribute">  
   ...  
   <AttributeRelationships>  
      <AttributeRelationship>...</AttributeRelationship>  
   </AttributeRelationships>  
   ...  
</Attribute>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Attribute](../objects/attribute-element-assl.md) of type [DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md)|  
|Child elements|[AttributeRelationship](../objects/attributerelationship-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.AttributeRelationshipCollection>.  

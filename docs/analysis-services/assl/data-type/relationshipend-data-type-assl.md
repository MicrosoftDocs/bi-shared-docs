---
title: "RelationshipEnd Data Type (ASSL) | Microsoft Docs"
description: Learn about the RelationshipEnd data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# RelationshipEnd Data Type (ASSL)

  Defines a primitive data type that represents a relationship end in a relationship.  
  
## Syntax  
  
```xml  
  
<RelationshipEnd>  
   <Role>...</Role>  
   <Multiplicity>...</Multiplicity>  
   <DimensionID>...</DimensionID>  
   <Attributes>...</Attributes>  
   <Translations>...</Translations>  
   <VisualizationProperties>...</VisualizationProperties>  
</Relationship>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|None|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Relationship](relationship-data-type-assl.md)|  
|Child elements|[Role](../../xmla/xml-elements-properties/role-element-xmla.md), [Multiplicity](../properties/multiplicity-element-assl.md), [DimensionID](../properties/dimensionid-element-assl.md), [Attributes](../collections/attributes-element-assl.md), [Translations](../collections/translations-element-assl.md), [VisualizationProperties](relationshipendvisualizationproperties-data-type-assl.md)|  
|Derived elements||  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.RelationshipEnd>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  

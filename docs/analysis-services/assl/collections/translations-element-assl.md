---
title: "Translations Element (ASSL) | Microsoft Docs"
description: Learn about the Translations collection element in the Analysis Services Scripting Language (ASSL) schema.
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
# Translations Element (ASSL)

  Contains the collection of [Translation](../objects/translation-element-assl.md) elements associated with the parent element.  
  
## Syntax  
  
```xml  
  
<Action><!-- or one of the elements listed below in the Element Relationships table -->  
   ...  
   <Translations>  
      <Translation>...</Translation>  
      <!-- or -->  
      <Translation xsi:type="AttributeTranslation">...</Translation><!-- parent: DimensionAttribute or ScalarMiningStructureColumn -->  
      <!-- or -->  
      <Translation xsi:type="RelationshipEndTranslation">...</Translation><!-- parent: RelationshipEnd -->  
   </Translations>  
   ...  
</Action>  
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
|Parent elements|[Action](../objects/action-element-assl.md), [AttributeRelationship](../objects/attributerelationship-element-assl.md), [CalculationProperty](../objects/calculationproperty-element-assl.md), [Cube](../objects/cube-element-assl.md), [CubeDimension](../data-type/cubedimension-data-type-assl.md), [Database](../objects/database-element-assl.md), [Dimension](../objects/dimension-element-assl.md), [DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md), [Hierarchy](../objects/hierarchy-element-assl.md), [Kpi](../objects/kpi-element-assl.md), [Level](../objects/level-element-assl.md), [Measure](../objects/measure-element-assl.md), [MiningModel](../objects/miningmodel-element-assl.md), [MiningModelColumn](../data-type/miningmodelcolumn-data-type-assl.md), [MiningStructure](../objects/miningstructure-element-assl.md), [Perspective](../objects/perspective-element-assl.md), [RelationshipEnd](../data-type/relationshipend-data-type-assl.md), [ScalarMiningStructureColumn](../data-type/scalarminingstructurecolumn-data-type-assl.md), [TableMiningStructureColumn](../data-type/tableminingstructurecolumn-data-type-assl.md)|  
|Child elements|See the table below.|  
  
|Ancestor or Parent|Child Element|  
|------------------------|-------------------|  
|[DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md) or [ScalarMiningStructureColumn](../data-type/scalarminingstructurecolumn-data-type-assl.md)|[Translation](../objects/translation-element-assl.md) of type [AttributeTranslation](../data-type/attributetranslation-data-type-assl.md)|  
|[RelationshipEnd](../data-type/relationshipend-data-type-assl.md)|[Translation](../data-type/relationshipendtranslation-element-assl.md) of type [RelationshipEndTranslation](../data-type/relationshipendtranslation-element-assl.md)|  
|All others|[Translation](../objects/translation-element-assl.md)|  
  
## Remarks  
 The corresponding elements in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.TranslationCollection> and <xref:Microsoft.AnalysisServices.AttributeTranslationCollection>.  

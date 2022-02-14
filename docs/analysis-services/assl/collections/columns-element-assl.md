---
title: "Columns Element (ASSL) | Microsoft Docs"
description: Learn about the Columns collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Columns Element (ASSL)

  Contains the collection of columns associated with the parent element.  
  
## Syntax  
  
```xml  
  
<Action xsi:type="DrillThroughAction"> <!-- or one of the elements listed below in the Element Relationships table -->  
   <Columns>  
      <Column xsi:type="MeasureBinding">...</Column> <!-- parent: DrillThroughAction -->  
      <!-- or -->  
      <Column xsi:type="CubeAttributeBinding">...</Column> <!-- parent: DrillThroughAction -->  
      <!-- or -->  
      <Column xsi:type="EventColumn">...</Column> <!-- parent: Event -->  
      <!-- or -->  
      <Column xsi:type="MiningModelColumn">...</Column> <!-- parent: MiningModel or MiningModelColumn -->  
      <!-- or -->  
      <Column xsi:type="MiningStructureColumn">...</Column> <!-- parent: MiningStructure or TableMiningStructureColumn -->  
   </Columns>  
</DrillThroughAction>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|See the table below.|  
  
|Ancestor or Parent|Cardinality|  
|------------------------|-----------------|  
|[Event](../objects/event-element-assl.md)|1-1: Required element that occurs once and only once.|  
|All others|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Action](../objects/action-element-assl.md) of type [DrillThroughAction](../data-type/drillthroughaction-data-type-assl.md), [Event](../objects/event-element-assl.md), [MiningModel](../objects/miningmodel-element-assl.md), [MiningModelColumn](../data-type/miningmodelcolumn-data-type-assl.md), [MiningStructure](../objects/miningstructure-element-assl.md), [TableMiningStructureColumn](../data-type/tableminingstructurecolumn-data-type-assl.md)|  
|Child elements|See the table below.|  
  
|Ancestor or Parent|Child Elements|  
|------------------------|--------------------|  
|[DrillThroughAction](../data-type/drillthroughaction-data-type-assl.md)|[CubeAttributeBinding](../data-type/cubeattributebinding-data-type-assl.md) or [MeasureBinding](../data-type/measurebinding-data-type-assl.md)|  
|[Event](../objects/event-element-assl.md)|[EventColumn](../data-type/eventcolumn-data-type-assl.md)|  
|[MiningModel](../objects/miningmodel-element-assl.md), [MiningModelColumn](../data-type/miningmodelcolumn-data-type-assl.md)|[MiningModelColumn](../data-type/miningmodelcolumn-data-type-assl.md)|  
|[MiningStructure](../objects/miningstructure-element-assl.md), [TableMiningStructureColumn](../data-type/tableminingstructurecolumn-data-type-assl.md)|[MiningStructureColumn](../data-type/miningstructurecolumn-data-type-assl.md)|  
  
## Remarks  
 For **DrillThroughAction** elements, the **Columns** collection identifies the columns that contain data to be returned when the action is performed.  
  
 For **TableMiningStructureColumn** elements, the **Columns** collection allows only one level of recursion. In other words, any **TableMiningStructureColumn** element included in this collection cannot contain any **TableMiningStructureColumn** elements in its **Columns** collection.  
  
 Some of the corresponding elements in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.TraceColumnCollection>, <xref:Microsoft.AnalysisServices.MiningModelColumnCollection>, and <xref:Microsoft.AnalysisServices.MiningStructureColumnCollection>.  


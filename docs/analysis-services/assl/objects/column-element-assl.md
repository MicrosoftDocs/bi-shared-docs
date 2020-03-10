---
title: "Column Element (ASSL) | Microsoft Docs"
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
# Column Element (ASSL)

  Describes a column in the collection of columns associated with the parent element.  
  
## Syntax  
  
```xml  
  
<Columns>  
   <Column xsi:type="MeasureBinding">...</Column> <!-- parent of collection: DrillThroughAction -->  
   <!-- or -->  
   <Column xsi:type="CubeAttributeBinding">...</Column> <!-- parent of collection: DrillThroughAction -->  
   <!-- or -->  
   <Column xsi:type="EventColumn">...</Column> <!-- parent of collection: Event -->  
   <!-- or -->  
   <Column xsi:type="MiningModelColumn">...</Column> <!-- parent of collection: MiningModel or MiningModelColumn -->  
   <!-- or -->  
   <Column xsi:type="MiningStructureColumn">...</Column> <!-- parent of collection: MiningStructure or TableMiningStructureColumn -->  
</Columns>  
```  
  
## Element Characteristics  
 **Data type and length**  
  
|Ancestor or Parent|Data Type|  
|------------------------|---------------|  
|[DrillThroughAction](../data-type/drillthroughaction-data-type-assl.md)|[MeasureBinding](../data-type/measurebinding-data-type-assl.md), [CubeAttributeBinding](../data-type/cubeattributebinding-data-type-assl.md)|  
|[Event](../objects/event-element-assl.md)|[EventColumn](../data-type/eventcolumn-data-type-assl.md)|  
|[MiningModel](../objects/miningmodel-element-assl.md), [MiningModelColumn](../data-type/miningmodelcolumn-data-type-assl.md)|[MiningModelColumn](../data-type/miningmodelcolumn-data-type-assl.md)|  
|[MiningStructure](../objects/miningstructure-element-assl.md), [TableMiningStructureColumn](../data-type/tableminingstructurecolumn-data-type-assl.md)|[MiningStructureColumn](../data-type/miningstructurecolumn-data-type-assl.md)|  
  
 **Default value**: None  
  
 **Cardinality**  
  
|Ancestor or Parent|Cardinality|  
|------------------------|-----------------|  
|[Event](../objects/event-element-assl.md)|1-n: Required element that can occur more than once.|  
|All others|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Columns](../collections/columns-element-assl.md)|  
|Child elements|None|  
  
## See Also  
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

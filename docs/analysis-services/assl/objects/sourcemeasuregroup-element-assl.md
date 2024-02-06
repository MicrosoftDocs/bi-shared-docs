---
title: "SourceMeasureGroup Element (ASSL) | Microsoft Docs"
description: Learn about the SourceMeasureGroup object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# SourceMeasureGroup Element (ASSL)

  Identifies the measure group that serves as the data source for a mining structure column.  
  
## Syntax  
  
```xml  
  
<MiningStructureColumn xsi:type="TableMiningStructureColumn">  
   ...  
   <SourceMeasureGroup xsi:type="MeasureGroupBinding">...</SourceMeasureGroup>  
   ...  
</MiningStructureColumn>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[MeasureGroupBinding](../data-type/measuregroupbinding-data-type-assl.md)|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[MiningStructureColumn](../data-type/miningstructurecolumn-data-type-assl.md) of type [TableMiningStructureColumn](../data-type/tableminingstructurecolumn-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 For more information about the **Binding** type, including tables of Analysis Services Scripting Language (ASSL) objects of the **Binding** type and the inheritance hierarchy of **Binding** types, see [Binding Data Type &#40;ASSL&#41;](../data-type/binding-data-type-assl.md).  
  
 The elements that correspond to the parents of **SourceMeasureGroup** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.MiningStructureColumn> and <xref:Microsoft.AnalysisServices.TableMiningStructureColumn>.  
  

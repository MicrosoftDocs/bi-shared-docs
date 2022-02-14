---
title: "Collation Element (ASSL) | Microsoft Docs"
description: Learn about the Collation property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Collation Element (ASSL)

  Determines the collation used by the parent element.  
  
## Syntax  
  
```xml  
  
<Database> <!-- or one of the elements listed below in the Element Relationships table -->  
   ...  
   <Collation>...</Collation>  
   ...  
</Database>  
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
|Parent elements|[Cube](../objects/cube-element-assl.md), [Database](../objects/database-element-assl.md), [DataItem](../data-type/dataitem-data-type-assl.md), [Dimension](../objects/dimension-element-assl.md), [MiningModel](../objects/miningmodel-element-assl.md), [MiningStructure](../objects/miningstructure-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The **Collation** string consists of the locale identifier (LCID) and the comparison flag, separated by an underscore character. For example, Latin1_General_CI_AS is an acceptable string.  
  
 The elements that correspond to the parents of **Collation** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.Cube>, <xref:Microsoft.AnalysisServices.Database>, <xref:Microsoft.AnalysisServices.DataItem>, <xref:Microsoft.AnalysisServices.Dimension>, <xref:Microsoft.AnalysisServices.MiningModel>, and <xref:Microsoft.AnalysisServices.MiningStructure>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

---
title: "LastProcessed Element (ASSL) | Microsoft Docs"
ms.date: 7/25/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
---
# LastProcessed Element (ASSL)

  Contains the read-only timestamp that indicates when the database that contains the parent element was last processed.  
  
## Syntax  
  
```xml  
  
<Cube> <!-- or one of the elements listed in the Element Relationships table -->  
   ...  
      <LastProcessed>...</LastProcessed>  
   ...  
</Cube>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|DateTime|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Cube](objects/cube-element-assl.md), [Database](objects/database-element-assl.md), [Dimension](objects/dimension-element-assl.md), [MeasureGroup](objects/measuregroup-element-assl.md), [MiningModel](objects/miningmodel-element-assl.md), [MiningStructure](objects/miningstructure-element-assl.md), [Partition](objects/partition-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The instance of Analysis Services maintains the value of the **LastProcessed** element. The value changes only if the database that contains the parent element is processed. Processing the parent element individually does not change the value of the **LastProcessed** element.  
  
 The elements that correspond to the parents of **LastProcessed** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.Cube>, <xref:Microsoft.AnalysisServices.Database>, <xref:Microsoft.AnalysisServices.Dimension>, <xref:Microsoft.AnalysisServices.MeasureGroup>, <xref:Microsoft.AnalysisServices.MiningModel>, <xref:Microsoft.AnalysisServices.MiningStructure>, and <xref:Microsoft.AnalysisServices.Partition>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties/properties-assl.md)  
  
  

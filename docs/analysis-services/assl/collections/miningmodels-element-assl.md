---
title: "MiningModels Element (ASSL) | Microsoft Docs"
description: Learn about the MiningModels collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# MiningModels Element (ASSL)

  Contains the collection of [MiningModel](../objects/miningmodel-element-assl.md) elements associated with a [MiningStructure](../objects/miningstructure-element-assl.md).  
  
## Syntax  
  
```xml  
  
<MiningStructure>  
   ...  
   <MiningModels>  
      <MiningModel>...</MiningModel>  
   </MiningModels>  
   ...  
</MiningStructure>  
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
|Parent elements|[MiningStructure](../objects/miningstructure-element-assl.md)|  
|Child elements|[MiningModel](../objects/miningmodel-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MiningModelCollection>.  

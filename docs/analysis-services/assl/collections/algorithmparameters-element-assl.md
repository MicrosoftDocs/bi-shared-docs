---
title: "AlgorithmParameters Element (ASSL) | Microsoft Docs"
description: Learn about the AlgorithmParameters collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# AlgorithmParameters Element (ASSL)

  Contains the collection of parameters for the algorithm used by a [MiningModel](../objects/miningmodel-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<MiningModel>  
   ...  
   <AlgorithmParameters>  
      <AlgorithmParameter>...</AlgorithmParameter>  
   </AlgorithmParameters>  
   ...  
</MiningModel>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None (collection)|  
|Default value|None (collection)|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[MiningModel](../objects/miningmodel-element-assl.md)|  
|Child elements|[AlgorithmParameter](../objects/algorithmparameter-element-assl.md)|  
  
## Remarks  
 The **AlgorithmParameters** collection contains an extensible set of parameters, represented as name/value pairs, for a mining model algorithm. The set of applicable parameters is algorithm-dependent. For more information about algorithm parameters for a given algorithm, see the appropriate documentation for that algorithm.  
  
 Available algorithm parameters, including validation and display information, can be retrieved from the DMSCHEMA_MINING_SERVICE_PARAMETERS schema rowset.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.AlgorithmParameterCollection>.  

  

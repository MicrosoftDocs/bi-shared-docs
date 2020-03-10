---
title: "Algorithm Element (ASSL) | Microsoft Docs"
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Algorithm Element (ASSL)

  Defines the algorithm used by a [MiningModel](../objects/miningmodel-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<MiningModel>  
      ...  
   <Algorithm>...</Algorithm>  
      ...  
</MiningModel>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|1-1: Required element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[MiningModel](../objects/miningmodel-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of the **Algorithm** element is a string that identifies the algorithm. For example, the string could be *Microsoft_Naive_Bayes*, *Microsoft_Decision_Trees*, or *Microsoft_Clustering.* The string identifies algorithms supplied by  and custom algorithms supplied by the user. Available values for the **Algorithm** element can be retrieved from the SERVICE_NAME column of the DMSCHEMA_MINING_SERVICES schema rowset.  
  
 The element that corresponds to the parent of **Algorithm** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MiningModel>. A closely related element in the AMO object model is <xref:Microsoft.AnalysisServices.MiningModelAlgorithms>.  

  

---
title: "Usage Element (MiningModelColumn) (ASSL) | Microsoft Docs"
description: Learn about the Usage property element for MiningModelColumn in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# Usage Element (MiningModelColumn) (ASSL)

  Describes how the associated column in the parent [MiningStructure](../objects/miningstructure-element-assl.md) is used.  
  
## Syntax  
  
```xml  
  
<MiningModelColumn>  
   ...  
   <Usage>...</Usage>  
   ...  
</MiningModelColumn>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[MiningModelColumn](../data-type/miningmodelcolumn-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Key*|The column is a key column.|  
|*Input*|The column is an input column.|  
|*Predict*|The column is a prediction column.|  
|*PredictOnly*|The column is a prediction column only.|  
|*None*|The column is not used by the model.<br /><br /> **\*\* Warning \*\*** When the value of Usage is "None", Analysis Services does not send any value to the server by default; hence, the Usage attribute is not included in the request/response.|  
  
 The enumeration that corresponds to the allowed values for **Usage** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MiningModelColumnUsages>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

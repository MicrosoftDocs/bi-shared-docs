---
title: "ModelingFlag Element (ASSL) | Microsoft Docs"
description: Learn about the ModelingFlag object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference

---
# ModelingFlag Element (ASSL)

  Contains a modeling flag for a column in a mining structure or a mining model.  
  
## Syntax  
  
```xml  
  
<ModelingFlags>  
   <ModelingFlag xsi:type="MiningModelingFlag">...</ModelingFlag>  
</ModelingFlags>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[MiningModelingFlag](../data-type/miningmodelingflag-data-type-assl.md)|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[ModelingFlags](../collections/modelingflags-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 A closely related element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MiningModelingFlags>.  
  
## See Also  
 [MiningModel Element &#40;ASSL&#41;](../objects/miningmodel-element-assl.md)   
 [MiningStructure Element &#40;ASSL&#41;](../objects/miningstructure-element-assl.md)   
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

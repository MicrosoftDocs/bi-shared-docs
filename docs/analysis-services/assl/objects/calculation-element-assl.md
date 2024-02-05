---
title: "Calculation Element (ASSL) | Microsoft Docs"
description: Learn about the Calculation object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Calculation Element (ASSL)

  Asssociates a calculation with a [Perspective](../objects/perspective-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Calculations>  
   <Calculation xsi:type="PerspectiveCalculation">  
      </Calculation>  
</Calculations>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[PerspectiveCalculation](../data-type/perspectivecalculation-data-type-assl.md)|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Calculations](../collections/calculations-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The corresponding elements in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.CalculationType> and <xref:Microsoft.AnalysisServices.PerspectiveCalculationType>.  
  
## See Also  
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

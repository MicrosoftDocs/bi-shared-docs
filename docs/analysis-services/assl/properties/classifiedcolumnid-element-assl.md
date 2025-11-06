---
title: "ClassifiedColumnID Element (ASSL) | Microsoft Docs"
description: Learn about the ClassifiedColumnID property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference

---
# ClassifiedColumnID Element (ASSL)

  Contains the identifier (ID) of a related column that is classified by the [ScalarMiningStructureColumn](../data-type/scalarminingstructurecolumn-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<ClassifiedColumns>  
   <ClassifiedColumnID>...</<ClassifiedColumnID>  
</ClassifiedColumns>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[ClassifiedColumns](../collections/classifiedcolumns-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of the **ClassifiedColumns** collection in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn>.  
  
## See Also  
 [Content Element &#40;ASSL&#41;](content-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

---
title: "Application Element (ASSL) | Microsoft Docs"
description: Learn about the Application property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference

---
# Application Element (ASSL)

  Identifies the application associated with an [Action](../objects/action-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Action>  
   ...  
   <Application>...</Application>  
   ...  
</Action>  
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
|Parent element|[Action](../objects/action-element-assl.md) or one of its derived elements: [DrillThroughAction](../data-type/drillthroughaction-data-type-assl.md), [ReportAction](../data-type/reportaction-data-type-assl.md), [StandardAction](../data-type/standardaction-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The **Application** element can be used by client applications to determine which actions are applicable to a given client application. The client application is responsible for evaluating the value of this element.  
  
 The element that corresponds to the parent of **Application** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Action>.  
  
## See Also  
 [Actions Element &#40;ASSL&#41;](../collections/actions-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

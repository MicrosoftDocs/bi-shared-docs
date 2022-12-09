---
title: "OverrideBehavior Element (ASSL) | Microsoft Docs"
description: Learn about the OverrideBehavior property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: owend

ms.topic: reference
author: minewiskan
ms.author: owend

---
# OverrideBehavior Element (ASSL)

  Indicates the override behavior of the relationship described by an [AttributeRelationship](../objects/attributerelationship-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<AttributeRelationship>  
   ...  
   <OverrideBehavior>...</OverrideBehavior>  
   ...  
</AttributeRelationship>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Strong*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[AttributeRelationship](../objects/attributerelationship-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The **OverrideBehavior** element determines how positioning on the related attribute affects the positioning on the attribute  
  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Strong*|Indicates the override behavior of the relationship described by an AttributeRelationship element. Dictates how positioning on one attribute affects the position of the other.|  
|*None*|No effect.|  
  
 The enumeration that corresponds to the allowed values for **OverrideBehavior** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.OverrideBehavior>.  

  
  

---
title: "Optionality Element (ASSL) | Microsoft Docs"
description: Learn about the Optionality property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# Optionality Element (ASSL)

  Indicates the optionality of the members for an [AttributeRelationship](../objects/attributerelationship-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<AttributeRelationship>  
   ...  
   <Optionality>...</OPtionality>  
   ...  
</AttributeRelationship>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Mandatory*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[AttributeRelationship](../objects/attributerelationship-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Mandatory*|Each member in the related attribute has to be associated with at least one member in the attribute that owns the **AttributeRelationship** element.|  
|*Optional*|Each member in the related attribute does not have to be associated with at least one member in the attribute that owns the **AttributeRelationship** element.|  
  
 The enumeration that corresponds to the allowed values for **Cardinality** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Optionality>.  

  

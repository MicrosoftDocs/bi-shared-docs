---
title: "RelationshipType Element (ASSL) | Microsoft Docs"
description: Learn about the RelationshipType property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
---
# RelationshipType Element (ASSL)

  Indicates whether member relationships for an [AttributeRelationship](../objects/attributerelationship-element-assl.md) can be changed.  
  
## Syntax  
  
```xml  
  
<AttributeRelationship>  
   ...  
   <RelationshipType>...</RelationshipType>  
   ...  
</AttributeRelationship>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Flexible*|  
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
|*Rigid*|The member relationships between an attribute and a related attribute cannot be changed.|  
|*Flexible*|The member relationships between an attribute and a related attribute can be changed.|  
  
 For example, if **ZipCode** cannot change from one **City** to another, the relationship from **ZipCode** to **City** is marked as *Rigid*.  
  
 The enumeration that corresponds to the allowed values for **RelationshipType** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.RelationshipType>.  

  
  

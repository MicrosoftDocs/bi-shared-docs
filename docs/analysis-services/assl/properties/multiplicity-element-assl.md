---
title: "Multiplicity Element (ASSL) | Microsoft Docs"
description: Learn about the Multiplicity property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: owend

ms.topic: reference
author: minewiskan
ms.author: owend

---
# Multiplicity Element (ASSL)

  Indicates whether the attributes in the RelationshipEnd are at the “one” side or the “many” side of a relationship.  
  
## Syntax  
  
```xml  
  
<RelationshipEnd>  
   ...  
   <Multiplicity>...</Multiplicity>  
   ...  
</RelationshipEnd>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value||  
|Cardinality|1: Required element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[RelationshipEnd](../data-type/relationshipend-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*One*|This is the primary key end.|  
|*Many*|This is the foreign key end.|  
  
 The enumeration that corresponds to the allowed values for **role** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Multiplicity>.  
  
  

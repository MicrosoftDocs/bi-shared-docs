---
title: "ContextualNameRule Element (XML) | Microsoft Docs"
description: Learn how the ContextualNameRule element provides a hint on the best way to construct a composite name for the attribute.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# ContextualNameRule Element (XML)

  Provides a hint on the best way to construct a composite name for the attribute.  
  
## Syntax  
  
```xml  
  
<RelationshipEndVisualizationProperties>  
   ...  
   <ContextualNameRule>...</ContextualNameRule>  
   ...  
</RelationshipEndVisualizationProperties>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|-1|  
|Cardinality|0-1: Optional element that occurs once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[RelationshipEndVisualizationProperties](../../assl/data-type/relationshipendvisualizationproperties-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 Provides a hint to client applications about how to create unambiguous names for this attribute.  
  
 The value of the **ContextualNameRule** element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*None*|Use the name of the attribute.|  
|*Context*|Use the name of the incoming relationship.|  
|*Merge*|Following the rules of the application language, concatenate the name of the incoming relationship and the attribute name.|  
  
  

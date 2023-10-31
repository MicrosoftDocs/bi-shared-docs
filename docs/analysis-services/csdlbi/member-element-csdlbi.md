---
title: "Member Element (CSDLBI) | Microsoft Docs"
description: Learn about the Member element, a complex type whose attributes can appear in columns, measures, navigation properties, hierarchies, and levels.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Member Element (CSDLBI)

[!INCLUDE[csdl-archived](../includes/csdl-archived.md)]

  The Member element is a complex type that serves as the base for other elements.  
  
 Its attributes can appear in columns, measures, navigation properties, hierarchies, and levels.  
  
## Elements and Attributes  
 The following table lists the elements and attributes that define the Member element.  
  
|Name|Is Required|Description|  
|----------|-----------------|-----------------|  
|Name||The name given to the member (a column, measure, navigation property, hierarchy, or level) that is defined by the implementation of the TMember type|  
|Caption|Yes|The display name for the member.|  
|ContextualNameRule|Yes|The naming format that is used to disambiguate members. The contents of this attribute are defined by the ContextualNameRule simple type.|  
|Hidden||A Boolean value that indicates whether the member will be hidden from the client.<br /><br /> The default is false, meaning that columns are visible in the client.|  
|ReferenceName||The identifier that is used to reference the member in a DAX query. If this attribute is omitted, the field name is used|  
  
## ContextualNameRule Element  
 This simple type defines the naming format that is used to disambiguate members.  
  
|Value|Description|  
|-----------|-----------------|  
|None|Use the attribute name.|  
|Context|Use the incoming relationship name.|  
|Merge|Concatenate the incoming relationship name and the property name.|  
  

  
  

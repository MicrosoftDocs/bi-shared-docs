---
title: "BaseProperty Element (CSDLBI) | Microsoft Docs"
description: Learn about the BaseProperty element, a complex type that serves as the base for other elements and whose attributes can appear in columns and in measures.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# BaseProperty Element (CSDLBI)

[!INCLUDE[csdl-archived](../includes/csdl-archived.md)]

  The BaseProperty element is a complex type that serves as the base for other elements.  
  
 Its attributes can appear in columns and in measures.  
  
## Elements and Attributes  
 The following table lists the elements and attributes that define the BaseProperty element.  
  
|Name|Is Required|Description|  
|----------|-----------------|-----------------|  
|Alignment|No|The name given to the member (a column, measure, navigation property, hierarchy, or level) that is defined by the implementation of the Member type|  
|FormatString|No|The display name for the member.|  
|IsRightToLeft|No|A Boolean value that indicates whether the field contains text that can be read from right to left.<br /><br /> If this attribute is omitted, the default setting (of the model) is used.|  
|SortDirection|No|A value that indicates how the field values are typically sorted. The contents of this attribute are defined by the SortDirection simple type.<br /><br /> If this attribute is omitted, a sort direction is assigned based on the field's data type.|  
|Units|No|The symbol that is applied to field values to express units.<br /><br /> If omitted, the units are unknown.|  
  
## Alignment Element  
 This simple type defines the naming format that is used to disambiguate members.  
  
|Value|Description|  
|-----------|-----------------|  
|None|Use the attribute name.|  
|Context|Use the incoming relationship name.|  
|Merge|Concatenate the incoming relationship name and the property name, according to the rules of the current grammar.|  
  
## SortDirection Element  
 This simple type defines the naming format that is used to disambiguate members.  
  
|Value|Description|  
|-----------|-----------------|  
|None|Use the attribute name.|  
|Context|Use the incoming relationship name.|  
|Merge|Concatenate the incoming relationship name and the property name.|  
  

  

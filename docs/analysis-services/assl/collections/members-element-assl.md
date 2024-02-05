---
title: "Members Element (ASSL) | Microsoft Docs"
description: Learn about the Members collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Members Element (ASSL)

  Contains the collection of [Member](../objects/member-element-assl.md) elements of the parent element.  
  
## Syntax  
  
```xml  
  
<Group> <!-- or Role --<  
   ...  
   <Members>  
      <Member>...</Member>  
   </Members>  
   ...  
</Group>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Group](../objects/group-element-assl.md), [Role](../objects/role-element-assl.md)|  
|Child elements|[Member](../objects/member-element-assl.md)|  
  
## Remarks  
 The elements that correspond to the parents of **Members** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.Group> and <xref:Microsoft.AnalysisServices.Role>.  

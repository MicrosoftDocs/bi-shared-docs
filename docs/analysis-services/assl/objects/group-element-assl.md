---
title: "Group Element (ASSL) | Microsoft Docs"
description: Learn about the Group object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Group Element (ASSL)

  Defines a group of members bound to an attribute.  
  
## Syntax  
  
```xml  
  
<Groups>  
   <Group>  
      <Name>...</Name>  
      <Members>...</Members>  
   </Group>  
<Groups/>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|1-n: Required element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Groups](../collections/groups-element-assl.md)|  
|Child elements|[Members](../collections/members-element-assl.md), [Name](../properties/name-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Group>.  
  
## See Also  
 [UserDefinedGroupBinding Data Type &#40;ASSL&#41;](../data-type/userdefinedgroupbinding-data-type-assl.md)   
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

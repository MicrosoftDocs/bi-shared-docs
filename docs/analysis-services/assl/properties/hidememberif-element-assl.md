---
title: "HideMemberIf Element (ASSL) | Microsoft Docs"
description: Learn about the HideMemberIf property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 09/14/2020
ms.service: analysis-services
ms.custom: assl
ms.reviewer: eur

ms.topic: reference
author: eric-urban
ms.author: eur

---
# HideMemberIf Element (ASSL)

  Indicates whether and when a member in a level should be hidden from client applications.  
  
## Syntax  
  
```xml  
  
<Level>  
   ...  
   <HideMemberIf>...</HideMemberIf>  
   ...  
</Level>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Never*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[Level](../objects/level-element-assl.md)|  
|Child elements|None|  
  
## Remarks

 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Never*|Members are never hidden.|  
|*OnlyChildWithNoName*|A member is hidden when it is the only child of its parent and its name is empty.|  
|*OnlyChildWithParentName*|A member is hidden when it is the only child of its parent and its name is identical to that of its parent.|  
|*NoName*|A member is hidden when its name is empty.|  
|*ParentName*|A member is hidden when its name is identical to that of its parent.|  

 The enumeration that corresponds to the allowed values for **HideMemberIf** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.HideIfValue>.  
  
## See Also

 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

---
title: "UnknownMemberName Element (ASSL) | Microsoft Docs"
description: Learn about the UnknownMemberName property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# UnknownMemberName Element (ASSL)

  Contains the caption, in the default language of the dimension, for the unknown member of the dimension.  
  
## Syntax  
  
```xml  
  
<Dimension>  
      ...  
   <UnknownMemberName>...</UnknownMemberName>  
   ...  
</Dimension>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|*Unknown*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[Dimension](../objects/dimension-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of the **UnknownMemberName** element supplies the caption used for the unknown member. The member ID of the unknown member is *Dimension*.UnknownMember, where *Dimension* is the unique name of the dimension, and cannot be changed.  
  
 The element that corresponds to the parent of **UnknownMemberName** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Dimension>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

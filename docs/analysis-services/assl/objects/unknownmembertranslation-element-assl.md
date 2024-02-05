---
title: "UnknownMemberTranslation Element (ASSL) | Microsoft Docs"
description: Learn about the UnknownMemberTranslation object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# UnknownMemberTranslation Element (ASSL)

  Contains a translation for the caption of the [UnknownMember](../properties/unknownmember-element-assl.md) element for a [Dimension](../objects/dimension-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<UnknownMemberTranslations>  
   <UnknownMemberTranslation xsi:type="Translation">...</UnknownMemberTranslation>  
</UnknownMemberTranslations>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[Translation](../data-type/translation-data-type-assl.md)|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[UnknownMemberTranslations](../collections/unknownmembertranslations-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **UnknownMemberTranslation** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Dimension>.  
  
## See Also  
 [Translation Element &#40;ASSL&#41;](../objects/translation-element-assl.md)   
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

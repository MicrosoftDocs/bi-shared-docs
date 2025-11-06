---
title: "UnknownMemberTranslations Element (ASSL) | Microsoft Docs"
description: Learn about the UnknownMemberTranslations collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference

---
# UnknownMemberTranslations Element (ASSL)

  Contains the collection of translations for the caption of the [UnknownMember](../properties/unknownmember-element-assl.md) element of a dimension.  
  
## Syntax  
  
```xml  
  
<Dimension>  
   ...  
   <UnknownMemberTranslations>  
      <UnknownMemberTranslation xsi:type="Translation ">...</UnknownMemberTranslation>  
      </UnknownMemberTranslations>  
   ...  
</Dimension>  
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
|Parent elements|[Dimension](../objects/dimension-element-assl.md)|  
|Child elements|[UnknownMemberTranslation](../objects/unknownmembertranslation-element-assl.md) of type [Translation](../data-type/translation-data-type-assl.md)|  
  
## Remarks  
 The element that corresponds to the parent of **UnknownMemberTranslations** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Dimension>.  

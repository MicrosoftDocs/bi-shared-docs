---
title: "Translation Data Type (ASSL) | Microsoft Docs"
description: Learn about the Translation data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Translation Data Type (ASSL)

  Defines a primitive data type that represents a localized translation.  
  
## Syntax  
  
```xml  
  
<Translation>  
   <Language>...</Language>  
   <Caption>...</Caption>  
   <Description>...</Description>  
   <DisplayFolder>...</DisplayFolder>  
   <Annotations>...</Annotations>  
</Translation>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|None|  
|Derived data types|[AttributeTranslation](attributetranslation-data-type-assl.md)|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[Annotations](../collections/annotations-element-assl.md), [Caption](../properties/caption-element-assl.md), [Description](../properties/description-element-assl.md), [DisplayFolder](../properties/displayfolder-element-assl.md), [Language](../properties/language-element-assl.md)|  
|Derived elements|[AllMemberTranslation](../objects/allmembertranslation-element-assl.md), [AttributeAllMemberTranslation](../objects/attributeallmembertranslation-element-assl.md), [NamingTemplateTranslation](../objects/namingtemplatetranslation-element-assl.md), [UnknownMemberTranslation](../objects/unknownmembertranslation-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Translation>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  

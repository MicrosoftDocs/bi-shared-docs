---
title: "NamingTemplateTranslations Element (ASSL) | Microsoft Docs"
description: Learn about the NamingTemplateTranslations collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 07/25/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# NamingTemplateTranslations Element (ASSL)

  Provides a collection of localized translations for the [NamingTemplate](../properties/namingtemplate-element-assl.md) element of the parent, [DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md).  
  
## Syntax  
  
```xml  
  
<Attribute xsi:type="DimensionAttribute">  
   ...  
   <NamingTemplateTranslations>  
            <NamingTemplateTranslation xsi:type="Translation">...</NamingTemplateTranslation>  
...</NamingTemplateTranslations>  
   ...  
</Attribute>  
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
|Parent elements|[Attribute](../objects/attribute-element-assl.md) of type [DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md)|  
|Child elements|[NamingTemplateTranslation](../objects/namingtemplatetranslation-element-assl.md) of type [Translation](../objects/translation-element-assl.md)|  
  
## Remarks  
 The value of the **NamingTemplateTranslation** element is used only by parent attributes (in other words, the value of the [Usage](../properties/usage-element-dimensionattribute-assl.md) element of the parent **DimensionAttribute** is set to *Parent*.)  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.DimensionAttribute>.  

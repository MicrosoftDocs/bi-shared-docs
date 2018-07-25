---
title: "Translation Element (ASSL) | Microsoft Docs"
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
# Translation Element (ASSL)

  Provides a localized translation for the parent of the [Translations](../collections/translations-element-assl.md) collection.  
  
## Syntax  
  
```xml  
  
<Translations>  
   <Translation xsi:type="Translation">...</Translation>  
   <!-- or -->  
   <Translation xsi:type="AttributeTranslation">...</Translation>  
</Translations>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[Translation](data-type/translation-data-type-assl.md), [AttributeTranslation](data-type/attributetranslation-data-type-assl.md)|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Translations](../collections/translations-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Translation>.  
  
## See Also  
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

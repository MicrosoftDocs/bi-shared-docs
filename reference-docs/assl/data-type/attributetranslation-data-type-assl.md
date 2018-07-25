---
title: "AttributeTranslation Data Type (ASSL) | Microsoft Docs"
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
# AttributeTranslation Data Type (ASSL)

  Defines a derived data type that represents a translation associated with an [Attribute](../objects/attribute-element-assl.md) element  
  
## Syntax  
  
```xml  
  
<AttributeTranslation>  
   <!-- The following elements extend Translation -->  
   <CaptionColumn>...</CaptionColumn>  
   <MembersWithDataCaption>...</MembersWithDataCaption>  
</AttributeTranslation>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[Translation](translation-data-type-assl.md)|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[CaptionColumn](../../objects/captioncolumn-element-assl.md), [MembersWithDataCaption](../properties/memberswithdatacaption-element-assl.md)|  
|Derived elements|See [Translation](../objects/translation-element-assl.md) ([Translations](../collections/translations-element-assl.md) collection of [DimensionAttribute](dimensionattribute-data-type-assl.md) or [ScalarMiningStructureColumn](scalarminingstructurecolumn-data-type-assl.md))|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.AttributeTranslation>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  

---
title: "AttributeAllMemberTranslations Element (ASSL) | Microsoft Docs"
description: Learn about the AttributeAllMemberTranslations collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# AttributeAllMemberTranslations Element (ASSL)

  Contains the collection of translations for the caption of the All member of the dimension.  
  
## Syntax  
  
```xml  
  
<Dimension>  
   ...  
   <AttributeAllMemberTranslations>  
      <AttributeAllMemberTranslation xsi:type="Translation">...</AttributeAllMemberTranslation>  
   </AttributeAllMemberTranslations>  
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
|Child elements|[AttributeAllMemberTranslation](../objects/attributeallmembertranslation-element-assl.md)|  
  
## Remarks  
 The element that corresponds to the parent of **AttributeAllMemberTranslations** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Dimension>.  

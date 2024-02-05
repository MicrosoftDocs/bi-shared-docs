---
title: "AllMemberTranslations Element (ASSL) | Microsoft Docs"
description: Learn about the AllMemberTranslations collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# AllMemberTranslations Element (ASSL)

  Contains the collection of [Translation](../objects/translation-element-assl.md) elements for the caption of the All member of a [Hierarchy](../objects/hierarchy-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Hierarchy>  
   ...  
   <AllMemberTranslations>  
      <AllMemberTranslation xsi:type="Translation">...  
            </AllMemberTranslation>  
   </AllMemberTranslations>  
      ...  
</Hierarchy>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None (collection)|  
|Default value|None (collection)|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[Hierarchy](../objects/hierarchy-element-assl.md)|  
|Child elements|[AllMemberTranslation](../objects/allmembertranslation-element-assl.md)|  
  
## Remarks  
 The element corresponding to the parent of **AllMemberTranslations** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Hierarchy>.  

  

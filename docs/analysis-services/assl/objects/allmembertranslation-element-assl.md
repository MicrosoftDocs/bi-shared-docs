---
title: "AllMemberTranslation Element (ASSL) | Microsoft Docs"
description: Learn about the AllMemberTranslation object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference

---
# AllMemberTranslation Element (ASSL)

  Contains a translation for the caption of the All member of a [Hierarchy](../objects/hierarchy-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<AllMemberTranslations>  
   <AllMemberTranslation xsi:type="Translation">...  
   </AllMemberTranslation>  
</AllMemberTranslations>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[Translation](../objects/translation-element-assl.md)|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[AllMemberTranslations](../collections/allmembertranslations-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of the **AllMemberTranslations** collection in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Hierarchy>.  
  
## See Also  
 [Translation Element &#40;ASSL&#41;](../objects/translation-element-assl.md)   
 [Hierarchy Element &#40;ASSL&#41;](../objects/hierarchy-element-assl.md)   
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

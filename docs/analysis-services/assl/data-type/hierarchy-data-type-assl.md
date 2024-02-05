---
title: "Hierarchy Data Type (ASSL) | Microsoft Docs"
description: Learn about the Hierarchy data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Hierarchy Data Type (ASSL)

  Defines a primitive data type that represents a hierarchy in a dimension.  
  
## Syntax  
  
```xml  
  
<Hierarchy>  
   <Name>...</Name>  
   <ID>...</ID>  
   <Description>...</Description>  
   <DisplayFolder>...</DisplayFolder>  
   <Translations>...</Translations>  
   <AllMemberName>...</AllMemberName>  
   <AllMemberTranslations>...</AllMemberTranslation>  
   <MemberNamesUnique>...</MemberNamesUnique>  
   <AllowDuplicateNames>...</AllowDuplicateNames>  
   <Levels>...</Levels>  
   <Annotations>...</Annotation>  
</Hierarchy>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|None|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[AllMemberName](../properties/allmembername-element-assl.md), [AllMemberTranslations](../collections/allmembertranslations-element-assl.md), [AllowDuplicateNames](../properties/allowduplicatenames-element-assl.md), [Annotations](../collections/annotations-element-assl.md), [Description](../properties/description-element-assl.md), [DisplayFolder](../properties/displayfolder-element-assl.md), [ID](../properties/id-element-assl.md), [Levels](../collections/levels-element-assl.md), [MemberNamesUnique](../properties/membernamesunique-element-assl.md), [Name](../properties/name-element-assl.md), [Translations](../collections/translations-element-assl.md)|  
|Derived elements|[Hierarchy](../objects/hierarchy-element-assl.md)|  
  
## Remarks  
 The *MemberNamesUnique* element is not supported under DevelopmentMode 1 or 2 for SharePoint or Tabular server modes, respectively.  
  
 The *MemberKeysUnique* element is not supported under DevelopmentMode 1 or 2 for SharePoint or Tabular server modes, respectively.  
  
 The *AllowDuplicateNames* element is not supported under DevelopmentMode 1 or 2 for SharePoint or Tabular server modes, respectively.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Hierarchy>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  

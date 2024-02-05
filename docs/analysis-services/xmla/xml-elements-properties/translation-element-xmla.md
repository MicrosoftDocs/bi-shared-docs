---
title: "Translation Element (XMLA) | Microsoft Docs"
description: Learn how the Translation element defines a translation for an attribute member.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Translation Element (XMLA)

  Defines a translation for an attribute member.  
  
## Syntax  
  
```xml  
  
<Translations>  
   ...  
   <Translation>  
      <Language>...</Language>  
      <Name>...</Name>  
   </Translation>  
   ...  
</Translations>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Translations](../xml-elements-properties/translations-element-xmla.md)|  
|Child elements|[Language](../xml-elements-properties/language-element-xmla.md), [Name](../xml-elements-properties/name-element-xmla.md)|  
  
## Remarks  
 A **Translation** element defines the information needed to associate an attribute member to a translation defined for a given attribute during an [Insert](../xml-elements-commands/insert-element-xmla.md) or [Update](../xml-elements-commands/update-element-xmla.md) command. 
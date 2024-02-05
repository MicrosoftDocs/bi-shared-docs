---
title: "Language Element (XMLA) | Microsoft Docs"
description: Learn how the Language element contains the locale identifier (LCID) for the parent Translation element.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Language Element (XMLA)

  Contains the locale identifier (LCID) for the parent [Translation](../xml-elements-properties/translation-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<Translation>  
   ...  
   <Language>...</Language>  
   ...  
</Translation>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Integer|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Translation](../xml-elements-properties/translation-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **Language** element specifies the LCID used by the parent **Translation** element to assign the **Name** element of the parent **Translation** element to an attribute member, for the specified language, during an **Insert** or **Update** command.  

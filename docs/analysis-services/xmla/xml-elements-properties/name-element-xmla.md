---
title: "Name Element (XMLA) | Microsoft Docs"
description: Learn how the Name element contains the name of an attribute member for the parent Attribute or Translation element.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Name Element (XMLA)

  Contains the name of an attribute member for the parent [Attribute](../xml-elements-properties/attribute-element-xmla.md) or [Translation](../xml-elements-properties/translation-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<Attribute> <!-- or Translation -->  
   ...  
   <Name>...</Name>  
   ...  
</Attribute>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|See the table below.|  
  
|Ancestor or Parent|Cardinality|  
|------------------------|-----------------|  
|[Attribute](../xml-elements-properties/attribute-element-xmla.md)|1-1: Required element that occurs once and only once.|  
|[Translation](../xml-elements-properties/translation-element-xmla.md)|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Attribute](../xml-elements-properties/attribute-element-xmla.md), [Translation](../xml-elements-properties/translation-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 For **Attribute** elements, the **Name** element contains the name of the attribute member to be inserted or updated during, respectively, the **Insert** or **Update** command.  
  
 For **Translation** elements, the **Name** element contains the caption of the attribute member, in the language specified by the **Language** element of the parent **Translation** object. If the **Name** element is not specified or contains an empty string, the value of the **Name** element for the **Attribute** element that contains the **Translation** element is used.  

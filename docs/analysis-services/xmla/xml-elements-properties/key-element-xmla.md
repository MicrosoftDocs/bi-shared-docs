---
title: "Key Element (XMLA) | Microsoft Docs"
description: Learn how the Key element contains a member key value for an attribute member.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Key Element (XMLA)

  Contains a member key value for an attribute member.  
  
## Syntax  
  
```xml  
  
<Keys>  
   ...  
   <Key>...</Key>  
   ...  
</Keys>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Any|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Keys](../xml-elements-properties/keys-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The data type used by this element should match the data type of the appropriate key column of the specified attribute. If **Key** elements are not specified for a parent **Attribute** element, the **AttributeName** and **Name** elements specified in the parent **Attribute** element are used to identify the attribute member to be modified.  
  
## See also
 [Attribute Element &#40;XMLA&#41;](../xml-elements-properties/attribute-element-xmla.md)   
 [AttributeName Element &#40;XMLA&#41;](../xml-elements-properties/attributename-element-xmla.md)   
 [Drop Element &#40;XMLA&#41;](../xml-elements-commands/drop-element-xmla.md)   
 [Insert Element &#40;XMLA&#41;](../xml-elements-commands/insert-element-xmla.md)   
 [KeyColumn Element &#40;ASSL&#41;](../../assl/objects/keycolumn-element-assl.md)   
 [Update Element &#40;XMLA&#41;](../xml-elements-commands/update-element-xmla.md)   
 [Where Element &#40;XMLA&#41;](../xml-elements-properties/where-element-xmla.md)   
 [Properties &#40;XMLA&#41;](../xml-elements-properties/xml-elements-properties.md)  
  
  

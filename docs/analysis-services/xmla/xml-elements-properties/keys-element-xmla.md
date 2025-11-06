---
title: "Keys Element (XMLA) | Microsoft Docs"
description: Learn how the Keys element contains a collection of Key elements used to identify the member keys of the attribute member represented by the parent Attribute element. 
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference

---
# Keys Element (XMLA)

  Contains a collection of [Key](../xml-elements-properties/key-element-xmla.md) elements used to identify the member keys of the attribute member represented by the parent [Attribute](../xml-elements-properties/attribute-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<Attribute>  
   ...  
   <Keys>  
      <Key>...</Key>  
   </Keys>  
   ...  
</Attribute>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Attribute](../xml-elements-properties/attribute-element-xmla.md)|  
|Child elements|[Key](../xml-elements-properties/key-element-xmla.md)|  
  
## Remarks  
  
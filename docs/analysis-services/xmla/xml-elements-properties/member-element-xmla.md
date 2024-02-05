---
title: "Member Element (XMLA) | Microsoft Docs"
description: Learn how the Member element represents a single member in a parent Members or Tuple element.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Member Element (XMLA)

  Represents a single member in a parent [Members](../xml-elements-properties/members-element-xmla.md) or [Tuple](../xml-elements-properties/tuple-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<Members>  
   ...  
   <Member>  
      <UName>...</UName>  
      <Caption>...</Caption>  
      <LName>...</LName>  
      <LNum>...</LNum>  
      <DisplayInfo>...</DisplayInfo>  
   </Member>  
   ...  
</Members>  
<!-- or -->  
<Tuple>  
   ...  
   <Member Hierarchy="string">  
      <UName>...</UName>  
      <Caption>...</Caption>  
      <LName>...</LName>  
      <LNum>...</LNum>  
      <DisplayInfo>...</DisplayInfo>  
   </Member>  
   ...  
</Tuple>  
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
|Parent elements|[Members](../xml-elements-properties/members-element-xmla.md), [Tuple](../xml-elements-properties/tuple-element-xmla.md)|  
|Child elements|[Caption](../xml-elements-properties/caption-element-xmla.md), [DisplayInfo](../xml-elements-properties/displayinfo-element-xmla.md), [LName](../xml-elements-properties/lname-element-xmla.md), [LNum](../xml-elements-properties/lnum-element-xmla.md), [UName](../xml-elements-properties/uname-element-xmla.md)|  
  
## Attributes  
  
|Attribute|Description|  
|---------------|-----------------|  
|Hierarchy|Required **String** attribute (for parent **Tuple** elements only). The name of the hierarchy to which the member represented by the **Member** element belongs.|  
  
## Remarks  
 The **Member** element contains the information needed to identify and display a member within a given hierarchy. For parent **Members** elements, the hierarchy is already specified by the **Hierarchy** attribute of the parent element. For parent **Tuple** elements, the hierarchy is specified using the **Hierarchy** attribute of the **Member** element.  
 
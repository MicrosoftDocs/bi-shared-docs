---
title: "Value Element (Parameter) (XMLA) | Microsoft Docs"
description: Learn how the Value element (parameter) contains the value of a parameter represented by the Parameter element.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Value Element (Parameter) (XMLA)

  Contains the value of a parameter represented by the [Parameter](../xml-elements-properties/parameter-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<Parameter>  
   ...  
   <Value>...</Value>  
   ...  
</Parameter>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Any|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Parameter](../xml-elements-properties/parameter-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **Value** element can store any simple XML type, as well as the XML for Analysis (XMLA) **Rowset** data type, for parameters used by XMLA commands in the [Execute](../xml-elements-methods-execute.md) method.  

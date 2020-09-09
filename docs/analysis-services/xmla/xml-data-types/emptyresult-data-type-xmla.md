---
title: "EmptyResult Data Type (XMLA) | Microsoft Docs"
description: Learn how the EmptyResult data type defines a derived data type that represents a root element that does not return data from a Discover or method call.
ms.date: 07/24/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# EmptyResult Data Type (XMLA)

  Defines a derived data type that represents a [root](../xml-elements-properties/root-element-xmla.md) element that does not return data from a [Discover](../xml-elements-methods-discover.md) or [Execute](../xml-elements-methods-execute.md) method call.  
  
 **Namespace** urn:schemas-microsoft-com:xml-analysis:empty  
  
## Syntax  
  
```xml  
  
<root xmlns="urn:schemas-microsoft-com:xml-analysis:empty">  
   <!-- All elements are inherited from Resultset -->  
</root>  
```  
  
## Data type characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[Resultset](../xml-data-types/resultset-data-type-xmla.md)|  
|Derived data types|None|  
  
## Data type relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|None|  
|Derived elements|[root](../xml-elements-properties/root-element-xmla.md)|  
  
## Remarks  
 Some XML for Analysis (XMLA) commands are not expected to return a result, or could not return a result because of an error. XMLA commands that do not return a result return the **EmptyResult** data type, a namespace on the **root** element.  
  
## Example  
 The following example represents a **root** element returned for an empty result.  
  
```xml  
<return>  
   <root xmlns="urn:schemas-microsoft-com:xml-analysis:empty"/>  
</return>  
```  
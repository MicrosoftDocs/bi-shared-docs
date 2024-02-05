---
title: "Statement Element (XMLA) | Microsoft Docs"
description: Learn how the Statement element contains a query or statement to be sent using the Execute method to an instance of Analysis Services.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Statement Element (XMLA)

  Contains a query or statement to be sent using the **Execute** method to an instance of Analysis Services.  
  
## Syntax  
  
```xml  
  
<Command>  
   <Statement>...</Statement>  
</Command>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Command](../xml-elements-properties/command-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **Statement** command executes a query or statement on the Analysis Services instance. Analysis Services supports the following languages:  
  
-   Multidimensional Expressions (MDX)  
  
-   Data Mining Extensions (MDX)  
  
-   A subset of Structured Query Language (SQL)  

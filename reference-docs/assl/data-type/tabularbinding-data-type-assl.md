---
title: "TabularBinding Data Type (ASSL) | Microsoft Docs"
ms.date: 07/25/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# TabularBinding Data Type (ASSL)

  Defines an abstract derived data type that represents a binding to a tabular item such as a table or a cube dimension.  
  
## Syntax  
  
```xml  
  
<TabularBinding>  
   <!-- The TabularBinding element has no child elements other than those inherited from Binding -->  
</TabularBinding>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[Binding](binding-data-type-assl.md)|  
|Derived data types|[DSVTableBinding](dsvtablebinding-data-type-assl.md), [QueryBinding](querybinding-data-type-assl.md), [TableBinding](tablebinding-data-type-assl.md)|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|None|  
|Derived elements|See [Binding](binding-data-type-assl.md)|  
  
## Remarks  
 For additional information about the **Binding** type, including tables of Analysis Services Scripting Language (ASSL) objects of the **Binding** type and the inheritance hierarchy of **Binding** types, see [Binding Data Type &#40;ASSL&#41;](binding-data-type-assl.md).  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is `<xref:Microsoft.AnalysisServices.TabularBinding>`.  
---
title: "QueryDefinition Element (ASSL) | Microsoft Docs"
description: Learn about the QueryDefinition property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: eur

ms.topic: reference
author: eric-urban
ms.author: eur

---
# QueryDefinition Element (ASSL)

  Contains an opaque expression for a query associated with a [DataSource](../objects/datasource-element-assl.md) element in a [QueryBinding](../data-type/querybinding-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<QueryBinding>  
   ...  
   <QueryDefinition>...</QueryDefinition>  
   ...  
</QueryBinding>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[QueryBinding](../data-type/querybinding-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **QueryDefinition** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.QueryBinding>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

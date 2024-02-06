---
title: "DataSourceViewID Element (ASSL) | Microsoft Docs"
description: Learn about the DataSourceViewID property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# DataSourceViewID Element (ASSL)

  Identifies the [DataSourceView](../objects/datasourceview-element-assl.md) element associated with the [Binding](../data-type/binding-data-type-assl.md) parent element.  
  
## Syntax  
  
```xml  
  
<DataSourceViewBinding> <!-- or DSVTableBinding -->  
   ...  
   <DataSourceViewID>...</DataSourceViewID>  
   ...  
</DataSourceViewBinding>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[DataSourceViewBinding](../data-type/datasourceviewbinding-data-type-assl.md), [DSVTableBinding](../data-type/dsvtablebinding-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The elements that correspond to the parents of **DataSourceViewID** in the Analysis Management Objects (AMO) object model are Microsoft.AnalysisServices.DataSourceViewBinding and Microsoft.AnalysisServices.DSVTableBinding.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

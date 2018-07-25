---
title: "DimensionBinding Data Type (ASSL) | Microsoft Docs"
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# DimensionBinding Data Type (ASSL)

  Defines a derived data type that represents the binding between a data source and a [Dimension](../objects/dimension-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<DimensionBinding>  
   <!-- The following elements extend Binding -->  
      <DataSourceID>...</DataSourceID>  
   <DimensionID>...</DimensionID>  
      <Persistence>...</Persistence>  
      <RefreshPolicy>...</RefreshPolicy>  
   <RefreshInterval>...</RefreshInterval>  
</DimensionBinding>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[Binding](binding-data-type-assl.md)|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[DataSourceID](../properties/datasourceid-element-assl.md), [DimensionID](../properties/dimensionid-element-assl.md), [Persistence](../properties/persistence-element-assl.md), [RefreshInterval](../properties/refreshinterval-element-assl.md), [RefreshPolicy](../properties/refreshpolicy-element-assl.md)|  
|Derived elements|See [Binding](binding-data-type-assl.md)|  
  
## Remarks  
 For additional information about the **Binding** type, including tables of Analysis Services Scripting Language (ASSL) objects of the **Binding** type and the inheritance hierarchy of **Binding** types, see [Binding Data Type &#40;ASSL&#41;](binding-data-type-assl.md) element.  
  
 For an overview of data bindings in ASSL, see [Data Sources and Bindings &#40;SSAS Multidimensional&#41;](../../../analysis-services/multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.DimensionBinding>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  

---
title: "CubeBinding Data Type (out-of-line) (ASSL) | Microsoft Docs"
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
# CubeBinding Data Type (out-of-line) (ASSL)

  Defines a primitive data type that represents the relationship between a [Cube](objects/cube-element-assl.md) element and a [DataSource](objects/datasource-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<CubeBinding>  
   <ID>...</ID>  
   <DataSourceID>...</DataSourceID>  
   <DataSource>...</DataSource>  
   <MeasureGroup>...</MeasureGroup>  
</CubeBinding>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|None|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[DataSource](objects/datasource-element-assl.md), [DataSourceID](properties/datasourceid-element-assl.md), [ID](properties/id-element-assl.md), [MeasureGroup](objects/measuregroup-element-assl.md)|  
|Derived elements|[Binding](../../../analysis-services/xmla/xml-elements-properties/binding-element-xmla.md) ([Bindings](../../../analysis-services/xmla/xml-elements-properties/bindings-element-xmla.md) collection of [Process](../../../analysis-services/xmla/xml-elements-commands/process-element-xmla.md) or [Batch](../../../analysis-services/xmla/xml-elements-commands/batch-element-xmla.md) commands)|  
  
## Remarks  
 For more information about out-of-line bindings, see [Data Sources and Bindings &#40;SSAS Multidimensional&#41;](../../../analysis-services/multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).  
  
## See Also  
 [Binding Data Type &#40;ASSL&#41;](data-type/binding-data-type-assl.md)   
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](data-type/analysis-services-scripting-language-xml-data-types-assl.md)  
  
  

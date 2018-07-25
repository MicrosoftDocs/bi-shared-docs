---
title: "DataSourceID Element (ASSL) | Microsoft Docs"
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# DataSourceID Element (ASSL)

  Identifies the [DataSource](objects/datasource-element-assl.md) element associated with the parent element.  
  
## Syntax  
  
```xml  
  
<CubeBinding> <!-- or one of the elements listed below in the Element Relationships table -->  
   ...  
   <DataSourceID>...</DataSourceID>  
   ...  
</CubeBinding>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|Depends on context|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[CubeBinding](data-type/cubebinding-data-type-out-of-line-assl.md), [CubeDimensionBinding](data-type/cubedimensionbinding-data-type-assl.md), [DimensionBinding](data-type/dimensionbinding-data-type-assl.md), [MeasureGroupBinding](data-type/measuregroupbinding-data-type-assl.md), [QueryBinding](data-type/querybinding-data-type-assl.md), [DataSourceView](objects/datasourceview-element-assl.md), [TableBinding](data-type/tablebinding-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The elements that correspond to the parents of **DataSourceID** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.CubeDimensionBinding>, <xref:Microsoft.AnalysisServices.DimensionBinding>, <xref:Microsoft.AnalysisServices.MeasureGroupBinding>, <xref:Microsoft.AnalysisServices.QueryBinding>, <xref:Microsoft.AnalysisServices.DataSourceView>, and <xref:Microsoft.AnalysisServices.TableBinding>.  
  
## See Also  
 [ID Element &#40;ASSL&#41;](properties/id-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties/properties-assl.md)  
  
  

---
title: "TableID Element (ASSL) | Microsoft Docs"
description: Learn about the TableID property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend

---
# TableID Element (ASSL)

  Contains the identifier (ID) of the table (from the [DataSourceView](../objects/datasourceview-element-assl.md) element) associated with the parent element.  
  
## Syntax  
  
```xml  
  
<ColumnBinding> <!-- or DSVTableBinding, RowBinding, IncrementalProcessingNotification -->  
   ...  
   <TableID>...</TableID>  
   ...  
</ColumnBinding>  
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
|Parent elements|[ColumnBinding](../data-type/columnbinding-data-type-assl.md), [DSVTableBinding](../data-type/dsvtablebinding-data-type-assl.md), [IncrementalProcessingNotification](../objects/incrementalprocessingnotification-element-assl.md), [RowBinding](../data-type/rowbinding-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The table identified by **TableID** must be within the data source to which the owning object (dimension or cube) is bound.  
  
 The elements that correspond to the parents of **TableID** in the Analysis Management Objects (AMO) object model are Microsoft.AnalysisServices.ColumnBinding>, <xref:Microsoft.AnalysisServices.DSVTableBinding, Microsoft.AnalysisServices.IncrementalProcessingNotification, and Microsoft.AnalysisServices.RowBinding.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

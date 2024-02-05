---
title: "ColumnID Element (ColumnBinding) (ASSL) | Microsoft Docs"
description: Learn about the ColumnID ColumnBinding property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# ColumnID Element (ColumnBinding) (ASSL)

  Contains the identifier (ID) of the column within the table to which the data item is bound.  
  
## Syntax  
  
```xml  
  
<ColumnBinding>  
   ...  
   <ColumnID>...</ColumnID>  
   ...  
</ColumnBinding>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|1-1: Required element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[ColumnBinding](../data-type/columnbinding-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **ColumnID** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ColumnBinding>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

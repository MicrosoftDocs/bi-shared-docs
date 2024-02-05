---
title: "ConnectionString Element (ASSL) | Microsoft Docs"
description: Learn about the ConnectionString property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# ConnectionString Element (ASSL)

  Contains the encrypted connection string for a [DataSource](../objects/datasource-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<DataSource>  
   ...  
   <ConnectionString>...</ConnectionString>  
   ...  
</DataSource>  
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
|Parent element|[DataSource](../objects/datasource-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **ConnectionString** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.DataSource>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

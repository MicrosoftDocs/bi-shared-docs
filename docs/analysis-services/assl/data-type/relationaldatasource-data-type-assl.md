---
title: "RelationalDataSource Data Type (ASSL) | Microsoft Docs"
description: Learn about the RelationalDataSource data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# RelationalDataSource Data Type (ASSL)

  Defines a derived data type that represents a [DataSource](../objects/datasource-element-assl.md) element based on a relational data source.  
  
## Syntax  
  
```xml  
  
<RelationalDataSource>  
   <!-- Child elements are only those inherited from DataSource -->  
</RelationalDataSource>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[DataSource](datasource-data-type-assl.md)|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|None|  
|Derived elements|[DataSource](../objects/datasource-element-assl.md) ([DataSources](../collections/datasources-element-assl.md) collection of [Database](../objects/database-element-assl.md))|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.RelationalDataSource>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  

---
title: "PushedDataSource Data Type (ASSL) | Microsoft Docs"
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
# PushedDataSource Data Type (ASSL)

  Defines a primitive data type that represents a data source (such as a Microsoft SQL Server Integration Services package) used for "pushing" data into a [Cube](../objects/cube-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<PushedDataSource>  
   <Root>...</Root>  
   <EndOfData>...</EndOfData>  
</PushedDataSource>  
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
|Child elements|[EndOfData](../properties/endofdata-element-assl.md), [Root](../properties/root-element-assl.md)|  
|Derived elements|None|  
  
## Remarks  
 **PushedDataSource** is used only within a processing command as an out-of-line data source. Persisted data sources are never of this type.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  

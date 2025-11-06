---
title: "PushedDataSource Data Type (ASSL) | Microsoft Docs"
description: Learn about the PushedDataSource data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference

---
# PushedDataSource Data Type (ASSL)

  Defines a primitive data type that represents a data source used for "pushing" data into a [Cube](../objects/cube-element-assl.md) element.  
  
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
  
  

---
title: "CubeBinding Data Type (out-of-line) (ASSL) | Microsoft Docs"
description: Learn about the CubeBinding data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# CubeBinding Data Type (out-of-line) (ASSL)

  Defines a primitive data type that represents the relationship between a [Cube](../objects/cube-element-assl.md) element and a [DataSource](../objects/datasource-element-assl.md) element.  
  
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
|Child elements|[DataSource](../objects/datasource-element-assl.md), [DataSourceID](../properties/datasourceid-element-assl.md), [ID](../properties/id-element-assl.md), [MeasureGroup](../objects/measuregroup-element-assl.md)|  
|Derived elements|[Binding](../../xmla/xml-elements-properties/binding-element-xmla.md) ([Bindings](../../xmla/xml-elements-properties/bindings-element-xmla.md) collection of [Process](../../xmla/xml-elements-commands/process-element-xmla.md) or [Batch](../../xmla/xml-elements-commands/batch-element-xmla.md) commands)|  
  
## Remarks  
  


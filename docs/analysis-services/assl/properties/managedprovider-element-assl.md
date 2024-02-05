---
title: "ManagedProvider Element (ASSL) | Microsoft Docs"
description: Learn about the ManagedProvider property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# ManagedProvider Element (ASSL)

  Contains the name of the managed provider used by an element that is derived from the [DataSource](../data-type/datasource-data-type-assl.md) data type.  
  
## Syntax  
  
```xml  
  
<DataSource>  
   ...  
   <ManagedProvider>...</ManagedProvider>  
   ...  
</DataSource>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[DataSource](../data-type/datasource-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 If a data source uses a managed provider, the **ManagedProvider** element contains the name of the managed provider.  
  
## See Also  
 [Name Element &#40;ASSL&#41;](name-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

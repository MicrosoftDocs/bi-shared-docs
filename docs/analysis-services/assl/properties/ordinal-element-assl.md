---
title: "Ordinal Element (ASSL) | Microsoft Docs"
description: Learn about the Ordinal property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
---
# Ordinal Element (ASSL)

  Indicates the ordinal number to bind to in collections such as keys and translations.  
  
## Syntax  
  
```xml  
  
<AttributeBinding> <!-- or CubeAttributeBinding -->  
   ...  
   <Ordinal>...</Ordinal>  
   ...  
</AttributeBinding>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Integer|  
|Default value|**0**|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[AttributeBinding](../data-type/attributebinding-data-type-assl.md), [CubeAttributeBinding](../data-type/cubeattributebinding-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 **AttributeBinding** and **CubeAttributeBinding** elements in which the [Type](type-element-binding-assl.md) property is set to either *Key* or *Translation* can be bound to an attribute that is in turn bound to a collection of columns in the data source view. The value of the **Ordinal** element determines to which column the **AttributeBinding** or **CubeAttributeBinding** refers in that collection.  
  
 The elements that correspond to the parents of **Ordinal** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.AttributeBinding> and <xref:Microsoft.AnalysisServices.CubeAttributeBinding>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

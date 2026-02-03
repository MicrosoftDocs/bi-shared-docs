---
title: "ProductName Element (ASSL) | Microsoft Docs"
description: Learn about the ProductName property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: eur

ms.topic: reference
author: eric-urban
ms.author: eur

---
# ProductName Element (ASSL)

  Contains the read-only product name of the instance of Analysis Services that is associated with a [Server](../objects/server-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Server>  
      ...  
      <ProductName>...</ProductName>  
   ...  
</Server>  
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
|Parent element|[Server](../objects/server-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The **ProductName** element provides read-only access to the name of the product associated with an instance ofAnalysis Services.  
  
 The element that corresponds to the parent of **ProductName** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Server>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

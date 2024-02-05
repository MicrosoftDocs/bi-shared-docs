---
title: "MaxActiveConnections Element (ASSL) | Microsoft Docs"
description: Learn about the MaxActiveConnections property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# MaxActiveConnections Element (ASSL)

  Contains the maximum number of concurrent connections allowed by an element that is derived from the [DataSource](../data-type/datasource-data-type-assl.md) data type.  
  
## Syntax  
  
```xml  
  
<DataSource>  
   ...  
   <MaxActiveConnections>...</MaxActiveConnections>  
   ...  
</DataSource>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Integer|  
|Default value|**10**|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[DataSource](../data-type/datasource-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 If the value of this element is set to zero, the maximum number of concurrent connections is determined by the data cartridge that is used to access the data source. If the value of this element is set to a negative value, the maximum number of concurrent connections is unlimited.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

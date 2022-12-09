---
title: "DataSourceImpersonationInfo Element (ASSL) | Microsoft Docs"
description: Learn about the DataSourceImpersonationInfo property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# DataSourceImpersonationInfo Element (ASSL)

  Contains the information used to determine impersonation behavior when connecting to the data source for a [Database](../objects/database-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Database>  
   <DataSourceImpersonationInfo>  
      <!-- Child elements are only those inherited from ImpersonationInfo -->  
   </DataSourceImpersonationInfo>  
</Database>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[ImpersonationInfo Data Type &#40;ASSL&#41;](../data-type/impersonationinfo-data-type-assl.md)|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Database](../objects/database-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

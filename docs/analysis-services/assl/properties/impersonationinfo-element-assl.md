---
title: "ImpersonationInfo Element (ASSL) | Microsoft Docs"
description: Learn about the ImpersonationInfo property element in the Analysis Services Scripting Language (ASSL) schema.
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
# ImpersonationInfo Element (ASSL)

  Contains the information that is used to determine impersonation behavior when accessing or executing an assembly.  
  
## Syntax  
  
```xml  
  
<Assembly> <!-- or one of the elements listed in the Element Relationships table -->  
   <ImpersonationInfo>  
      <!-- Child elements are only those that are inherited from ImpersonationInfo -->  
   </ImpersonationInfo>  
</Assembly>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[ImpersonationInfo](../data-type/impersonationinfo-data-type-assl.md)|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Assembly](../data-type/assembly-data-type-assl.md), [DataSource](../data-type/datasource-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

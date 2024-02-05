---
title: "Password Element (ASSL) | Microsoft Docs"
description: Learn about the Password property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# Password Element (ASSL)

  Contains the password of the user account for the [ImpersonationInfo](../data-type/impersonationinfo-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<ImpersonationInfo  
   ...  
  <Password>...</Password>  
   ...  
</ImpersonationInfo>  
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
|Parent element|[ImpersonationInfo](../data-type/impersonationinfo-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of the **Password** element, as well as the value of the [Account](account-element-impersonationinfo-assl.md) element, is used for impersonation purposes if the value of the [ImpersonationMode](impersonationmode-element-assl.md) element for any element derived from the **ImpersonationInfo** data type is set to *ImpersonateAccount*.  
  
 Only members of the server administrator role for theAnalysis Services instance can provide a blank value for the **Password** element  
  
## See Also  
 [DataSourceImpersonationInfo Element &#40;ASSL&#41;](datasourceimpersonationinfo-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

---
title: "Account Element (ImpersonationInfo) (ASSL) | Microsoft Docs"
description: Learn about the Account property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Account Element (ImpersonationInfo) (ASSL)

  Contains the name of the user account for the [ImpersonationInfo](../data-type/impersonationinfo-data-type-assl.md) data type.  
  
## Syntax  
  
```xml  
  
<ImpersonationInfo  
   ...  
  <Account>...</Account>  
   ...  
</Action>  
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
|Parent elements|[ImpersonationInfo](../data-type/impersonationinfo-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of the **Account** element, as well as the value of the [Password](password-element-assl.md) element, is used for impersonation purposes if the value of the [ImpersonationMode](impersonationmode-element-assl.md) element for any element derived from the **ImpersonationInfo** data type is set to *ImpersonateAccount*.  
  
## See Also  
 [DataSourceImpersonationInfo Element &#40;ASSL&#41;](datasourceimpersonationinfo-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

---
title: "ImpersonationMode Element (ASSL) | Microsoft Docs"
description: Learn about the ImpersonationMode property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# ImpersonationMode Element (ASSL)

  Contains a value that indicates the method of impersonation for elements that are derived from the [ImpersonationInfo](../data-type/impersonationinfo-data-type-assl.md) data type.  
  
## Syntax  
  
```xml  
  
<ImpersonationInfo>  
   ...  
   <ImpersonationMode>...</ImpersonationMode>  
  
</ImpersonationInfo>...  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Default*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[ImpersonationInfo](../data-type/impersonationinfo-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Default*|The parent uses the impersonation method that is most appropriate for the context in which impersonation is used.|  
|*ImpersonateAccount*|The parent uses the credentials of the user account that is specified in the parent element.|  
|*ImpersonateAnonymous*|The parent uses the credentials of an anonymous user.|  
|*ImpersonateCurrentUser*|The parent uses the credentials of the current user.|  
|*ImpersonateServiceAccount*|The parent uses the credentials of the service account that is associated with the instance of Analysis Services.|  
  
 The enumeration that corresponds to the allowed values for **ImpersonationMode** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ImpersonationLevel>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

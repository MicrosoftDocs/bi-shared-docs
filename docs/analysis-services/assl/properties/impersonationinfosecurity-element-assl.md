---
title: "ImpersonationInfoSecurity Element (ASSL) | Microsoft Docs"
description: Learn about the ImpersonationInfoSecurity property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend

---
# ImpersonationInfoSecurity Element (ASSL)

  Contains a read-only value that indicates if any changes were made to the security credentials that are supplied in the [ImpersonationInfo](../data-type/impersonationinfo-data-type-assl.md) data type.  
  
## Syntax  
  
```xml  
  
<ImpersonationInfo>  
   ...  
   <ImpersonationInfoSecurity>...</ImpersonationInfoSecurity>  
  
</ImpersonationInfo>...  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|None|  
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
|*PasswordRemoved*|Password information has been removed from the supplied security credentials.|  
|*Unchanged*|No changes have been made to the supplied security credentials.|  
  
 The enumeration that corresponds to the allowed values for **ImpersonationInfoSecurity** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ImpersonationInfoSecurity>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

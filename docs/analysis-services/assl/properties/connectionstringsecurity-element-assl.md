---
title: "ConnectionStringSecurity Element (ASSL) | Microsoft Docs"
description: Learn about the ConnectionStringSecurity property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# ConnectionStringSecurity Element (ASSL)

  Specifies whether the user's password is stripped from the data source connection string for security purposes.  
  
## Syntax  
  
```xml  
  
<DataSource>  
   ...  
   <ConnectionStringSecurity>...</ConnectionStringSecurity>  
   ...  
</DataSource>  
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
|Parent element|[DataSource](../objects/datasource-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*PasswordRemoved*|The password has been stripped from the connection string.|  
|*Unchanged*|The connection string has not been modified.|  
  
 The enumeration corresponding to the allowed values for **ConnectionStringSecurity** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ConnectionStringSecurity>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

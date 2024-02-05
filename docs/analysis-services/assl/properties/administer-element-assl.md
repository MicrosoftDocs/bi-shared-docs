---
title: "Administer Element (ASSL) | Microsoft Docs"
description: Learn about the Administer property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Administer Element (ASSL)

  Indicates whether the associated permission includes the right to administer a [Database](../objects/database-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<DatabasePermission>  
      ...  
      <Administer>...</Administer>  
   ...  
</DatabasePermission>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Boolean|  
|Default value|False|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[DatabasePermission](../objects/databasepermission-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The **Administer** element indicates whether a user can perform administrative functions only on the specified database. The server administrator role can perform administrative functions on all databases contained by the instance.  
  
 The element that corresponds to the parent of **Administer** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.DatabasePermission>.  
  
## See Also  
 [Permission Data Type &#40;ASSL&#41;](../data-type/permission-data-type-assl.md)   
 [Role Element &#40;ASSL&#41;](../objects/role-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

---
title: "Roles Element (ASSL) | Microsoft Docs"
description: Learn about the Roles collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Roles Element (ASSL)

  Contains the collection of [Role](../objects/role-element-assl.md) elements defined under the parent element.  
  
## Syntax  
  
```xml  
  
<Database> <!-- or Server -->  
   ...  
   <Roles>  
      <Role>...</Role>  
   </Roles>  
   ...  
</Database>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Database](../objects/database-element-assl.md), [Server](../objects/server-element-assl.md)|  
|Child elements|[Role](../objects/role-element-assl.md)|  
  
## Remarks  
 The **Roles** element associated with a **Server** element contains only one role, named Administrators, which represents the server administrator role. The server administrator role cannot be changed or deleted, nor can additional roles be added to the collection.  
  
 The **Roles** element associate with a **Database** element contains the roles defined for that database.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.RoleCollection>.  

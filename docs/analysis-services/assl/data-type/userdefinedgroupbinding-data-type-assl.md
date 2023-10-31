---
title: "UserDefinedGroupBinding Data Type (ASSL) | Microsoft Docs"
description: Learn about the UserDefinedGroupBinding data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# UserDefinedGroupBinding Data Type (ASSL)

  Defines a derived data type that represents a user-defined grouping for an attribute.  
  
## Syntax  
  
```xml  
  
<UserDefinedGroupBinding>  
   <!-- The following elements extend Binding -->  
      <AttributeID>...</AttributeID>  
      <Groups>...</Groups>  
</UserDefinedGroupBinding>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[Binding](binding-data-type-assl.md)|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[AttributeID](../properties/attributeid-element-assl.md), [Groups](../collections/groups-element-assl.md)|  
|Derived elements|See [Binding](binding-data-type-assl.md)|  
  
## Remarks  
 **UserDefinedGroupBinding** is automatically treated as an [AttributeBinding](attributebinding-data-type-assl.md), whose [Type](../properties/type-element-binding-assl.md) element is set to *All*.  
  
 For more information about the **Binding** type, including tables of Analysis Services Scripting Language (ASSL) objects of the **Binding** type and the inheritance hierarchy of **Binding** types, see [Binding Data Type &#40;ASSL&#41;](binding-data-type-assl.md). 
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.UserDefinedGroupBinding>.  
  
  

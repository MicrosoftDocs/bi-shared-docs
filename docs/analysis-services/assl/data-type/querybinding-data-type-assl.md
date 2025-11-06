---
title: "QueryBinding Data Type (ASSL) | Microsoft Docs"
description: Learn about the QueryBinding data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference

---
# QueryBinding Data Type (ASSL)

  Defines a derived data type that represents the association of a [DataSource](../objects/datasource-element-assl.md) element with a [QueryDefinition](../properties/querydefinition-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<QueryBinding>  
   <!-- The following elements extend TabularBinding -->  
   <DataSourceID>...</DataSourceID>  
      <QueryDefinition>...</QueryDefinition>  
</QueryBinding>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[TabularBinding](tabularbinding-data-type-assl.md)|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[DataSourceID](../properties/datasourceid-element-assl.md), [QueryDefinition](../properties/querydefinition-element-assl.md)|  
|Derived elements|See [Binding](binding-data-type-assl.md)|  
  
## Remarks  
 For more information about the **Binding** type, including tables of Analysis Services Scripting Language (ASSL) objects of the **Binding** type and the inheritance hierarchy of **Binding** types, see [Binding Data Type &#40;ASSL&#41;](binding-data-type-assl.md).  

 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.QueryBinding>.  
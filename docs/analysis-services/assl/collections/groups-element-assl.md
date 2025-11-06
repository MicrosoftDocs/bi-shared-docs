---
title: "Groups Element (ASSL) | Microsoft Docs"
description: Learn about the Groups collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference

---
# Groups Element (ASSL)

  Contains the collection of groups of members bound to an attribute.  
  
## Syntax  
  
```xml  
  
<Binding xsi:type="UserDefinedGroupBinding">  
   ...  
   <Groups>  
      <Group>...</Group>  
   </Groups>  
   ...  
</Binding>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Binding](../data-type/binding-data-type-assl.md) of type [UserDefinedGroupBinding](../data-type/userdefinedgroupbinding-data-type-assl.md)|  
|Child elements|[Group](../objects/group-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.GroupCollection>.  

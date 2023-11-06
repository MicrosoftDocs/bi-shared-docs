---
title: "AssociationSet Element (CSDLBI) | Microsoft Docs"
description: Learn about the AssociationSet element, a complex type that defines an association or relationship between two tables.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# AssociationSet Element (CSDLBI)

[!INCLUDE[csdl-archived](../includes/csdl-archived.md)]

  The **AssociationSet** element is a complex type that defines an association. In a CSDLBI data model, an association is a relationship between two tables.  
  
 An **AssociationSet** must be specified for each unique relationship in a model. The **AssociationSet** defines the endpoints by using the **Association** element. The **AssociationSet** element also defines metadata about the relationship and its usage in the data model.  
  
## Applicable Attributes  
 The following table lists the elements and attributes that define the **AssociationSet** element.  
  
|Name|Is Required|Description|  
|----------|-----------------|-----------------|  
|State|Yes|A string that indicates whether the association is active or not. The value is defined by the State element.|  
|Hidden|No|A Boolean value that indicates whether the relationship is visible. By default, the value of Hidden is **false**, meaning all relationships are visible in the model.|  
  
## State Element  
 The **State** element is a simple type that describes whether an association is active, and should be used in calculations, or is inactive, and must be explicitly referenced in calculations.  
  
 If there are multiple association sets connecting two entities, no more than one association set can be marked Active. In other words, if there are two relationships between the same two tables, only one relationship can be active.  
  
 The following table lists the values of the **State** element.  
  
|Value|Description|  
|-----------|-----------------|  
|Active|The association is active.|  
|Inactive|The association is active.|  
  
## Example Tabular  
  
 The following sample shows a relationship in the AdventureWorks tabular model) (in CSDLBI version 1.1). The association is marked as Inactive, because there is an existing relationship (between OrderKey and Date).  
  
```xml  
<AssociationSet   
    Name="InternetSales_Date_Date_Date"  
    Association="Sandbox.InternetSales_Date_Date_Date">  
    <End EntitySet="InternetSales" />  
    <End EntitySet="DimDate" />  
<bi:AssociationSet State="Inactive" />  
</AssociationSet>  
  
```  
  
## Example Multidimensional  
  
 The following sample shows the relationship that is defined between the Sales and Currency tables, in the Contoso Operations cube.  
  
```xml  
<AssociationSet   
    Name ="Sales_Currency_Currency_Currency_Name2"  
    Association ="Sandbox.Sales_Currency_Currency_Currency_Name2">  
    <End EntitySet ="Sales" />  
    <End EntitySet ="Currency" />  
<bi:AssociationSet />  
</AssociationSet>  
```  
  

  

---
title: "Property Element (CSDLBI) | Microsoft Docs"
description: Learn about the Property element, a complex type that provides additions to the CSDL Property element in support of business intelligence data models.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Property Element (CSDLBI)

[!INCLUDE[csdl-archived](../includes/csdl-archived.md)]

  The Property element in CSDLBI is a complex type that provides additions to the CSDL Property element, in support of business intelligence data models.  
  
## Elements and Attributes  
 The following table lists the elements and attributes that define the CSDLBI Property element.  
  
|Name|Is Required|Description|  
|----------|-----------------|-----------------|  
|Contents|No|A string that contains the LCID of the request.|  
|DefaultAggregationFunction|Yes|A string that specifies the aggregation function that should be used if calculations are performed over the attribute and no other function has been specified.<br /><br /> If not specified, the default aggregation for the model is used, which is typically SUM.|  
|GroupingBehavior|No|A value that specifies how query results are grouped. The attribute's contents are defined by the TGroupingBehavior simple type (see table below).|  
|OrderBy|No|A reference to another property within the model that defines the sort order for that property's values.<br /><br /> The values for the two properties SHOULD have a 1-to-1 mapping. Otherwise, the sort behavior is undefined.<br /><br /> If this element is omitted, the properties are sorted based on their values.|  
|Stability|No|An attribute that specifies the stability of the property values between refresh operations.<br /><br /> This attribute is not set by users, but is emitted by the design-time environment only for unstable values. It is always applied to columns that contain a row number, and to columns that contain formulas that generate indeterminate results, such as NOW() or RAND().<br /><br /> The values for this attribute are listed in the table below, that describes the Stabilitysimple type.|  
  
## GroupingBehavior  
 The following table lists the values of the GroupingBehavior simple type.  
  
|Value|Description|  
|-----------|-----------------|  
|GroupOnValue|Group by the value of xthe attribute.|  
|GroupOnEntityKey|Group by the entity key.|  
  
 The following example illustrates the usage of these two values. Suppose the query was designed to return payroll deductions for a certain user, specified by name. Assuming the database contains two users with the same name but different database identifiers, the query results would be different depending on which attribute value is applied to the column:  
  
-   **GroupOnValue**: Query results include the payroll deductions of both users, totaled together.  
  
-   **GroupOnEntityKey**: Query results include the payroll deductions for each user, but listed individually.  
  
## Stability  
 The following table lists the values of the **Stability** simple type.  
  
|Value|Description|  
|-----------|-----------------|  
|Stable|The property remains constant between refresh operations.|  
|RowNumber|The property contains a row number.|  
|Volatile|The property might not remain constant between refresh operations.|  
  
## Example Tabular
  
 The following XML shows the representation, in CSDLBI version 1.1, of some properties in the AdventureWorks tabular model sample.  
  
```xml   
  
<EntityType   
   Name="DimEmployee">  
   <Key>  
      <PropertyRef   
      Name="RowNumber" />  
   </Key>  
  
   <Property   
      Name="RowNumber"   
      Type="Int64"   
      Nullable="false">  
   <bi:Property   
      Hidden="true"   
      Contents="RowNumber"   
      Stability="RowNumber" />  
   </Property>  
  
   <Property   
      Name="EmployeeKey"   
      Type="Int64">  
   <bi:Property />  
   </Property>  
….  
</bi:EntityType>  
</EntityType>  
  
```  
  
## Example Multidimensional
  
 The following sample, in CSDLBI version 1.1, shows some properties for columns in the data model representing the Contoso Operations cube. Note that BI annotations are not required or applied to most columns, only those that require special handling in the presentation layer.  
  
```xml   
  
<EntityType   
   Name="Bike">  
  
   <Key>  
      <PropertyRef Name="RowNumber" />  
   </Key>  
  
   <Property   
      Name="RowNumber"   
      Type="Int64"   
      Nullable="false">  
   <bi:Property   
      Hidden="true"   
      Contents="RowNumber"   
      Stability="RowNumber"   
   />  
   </Property>  
  
   <Property   
      Name="ProductAlternateKey"   
      Type="String"   
      MaxLength="Max"   
      Unicode="true"   
      FixedLength="false">  
   <bi:Property />  
   </Property>  
  
```  

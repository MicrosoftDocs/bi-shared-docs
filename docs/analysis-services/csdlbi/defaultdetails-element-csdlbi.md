---
title: "DefaultDetails Element (CSDLBI) | Microsoft Docs"
description: Learn how the DefaultDetails element represents a list of property references that together define the "default field set" of columns in the table. 
ms.date: 07/19/2021
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# DefaultDetails Element (CSDLBI)

[!INCLUDE[csdl-archived](../includes/csdl-archived.md)]

  The DefaultDetails element represents a list of property references that together define the "default field set" of columns in the table. Each property can only refer to a measure or a column.  
  
## Elements and Attributes  
 The following table lists the elements and attributes that define the DefaultDetails element.  
  
|Name|Is Required|Description|  
|----------|-----------------|-----------------|  
|DefaultDetailsPosition|No|A positive integer that indicates presence and position in the collection.|  
  
## Example Tabular  
  
 The following example, in CSDLBI version 1.1, shows an excerpt from the AdventureWorks sample data model. There Is only one default column set for the Employees table (Title). However, three columns have been defined as the default field set for the Products table.  
  
```xml   
  
<EntityType   
    Name="DimEmployee">  
....  
   <bi:DefaultDetails>  
      <bi:MemberRef Name="Title" />  
   </bi:DefaultDetails>  
.....  
<EntityType   
    Name="Products">  
.....  
   <bi:DefaultDetails>  
      <bi:MemberRef Name="Color" />  
      <bi:MemberRef Name="DealerPrice" />  
      <bi:MemberRef Name="Status" />  
   </bi:DefaultDetails>  
  
```  
  
## Example Multidimensional  
  
 The following example, in CSDLBI version 1.1, shows an excerpt from the definition of the Bike table in the Contoso Operations cube. This annotation indicates that the Color column should be displayed by default if no other display column is specified.  
  
```xml   
  
<EntityType Name="Bike">  
   <Key>  
   <PropertyRef Name="RowNumber" />  
   </Key>  
....  
<bi:EntityType>  
   <bi:DisplayKey>  
      <bi:MemberRef Name="Color" />  
   </bi:DisplayKey>  
   <bi:DefaultDetails>  
      <bi:MemberRef Name="Color" />  
   </bi:DefaultDetails>  
   <bi:SortMembers>  
      <bi:MemberRef Name="Color" />  
   </bi:SortMembers>  
....  
</bi:EntityType>  
</EntityType>  
```  

  
  

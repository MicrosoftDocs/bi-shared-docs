---
title: "MemberRef Element (CSDLBI) | Microsoft Docs"
description: Learn about the MemberRefs element, which identifies the name of a property that is the target of a reference.
ms.date: 07/19/2021
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# MemberRef Element (CSDLBI)

[!INCLUDE[csdl-archived](../includes/csdl-archived.md)]

  The MemberRef element identifies the name of a property that is the target of a reference.  
  
## Elements and Attributes  
 The following table lists the elements and attributes that define the MemberRef element.  
  
|Name|Is Required|Description|  
|----------|-----------------|-----------------|  
|Name|Yes|he name of the property contained in a MemberRef element.|  
  
## MemberRefs Element  
 MemberRefs is a complex type that defines a collection of members in which each member is contained in a MemberRef element.  
  
 The following table lists the elements and attributes of the MemberRefs type.  
  
|Name|Is Required|Description|  
|----------|-----------------|-----------------|  
|MemberRef|Yes|A string containing the member reference.|  
  
## Example Tabular
  
 The following sample, in CSDLBI version 1.1, represents a portion of the AdventureWorks sample data model that defines the Products table. Here the MemberRef element is used for each column that is included in the default field set for the model.  
  
```xml   
  
<bi:EntityType>  
   <bi:DefaultDetails>  
     <bi:MemberRef Name="Color" />  
     <bi:MemberRef Name="DealerPrice" />  
     <bi:MemberRef Name="Status" />  
   </bi:DefaultDetails>  
  
```  
  
## Example Multidimensional 
  
 The following sample, in CSDLBI version 1.1, represents a portion of the Contoso Operations cube that defines the Bikes table. In this sample, a MemberRef element is used to specify the name of the column that is used as the default field set in reports, and another MemberRef element is used to reference the column that provides the sort order.  
  
```xml   
  
<bi:DefaultDetails>  
   <bi:MemberRef Name="Color" />  
</bi:DefaultDetails>  
  
<bi:SortMembers>  
   <bi:MemberRef Name="Color" />  
</bi:SortMembers>  
  
```  
  

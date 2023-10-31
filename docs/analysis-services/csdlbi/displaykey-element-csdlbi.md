---
title: "DisplayKey Element (CSDLBI) | Microsoft Docs"
description: Learn about the DisplayKey element, a child of the EntityType element that contains elements that together constitute a strong identifier.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# DisplayKey Element (CSDLBI)

[!INCLUDE[csdl-archived](../includes/csdl-archived.md)]

  The DisplayKey element contains a list of the following elements that together constitute a strong identifier. The DisplayKey is found only as a child of the EntityType element. It can reference either columns or role ends.  
  
## Elements and Attributes  
 The following table lists the attributes of the DisplayKey element.  
  
|Name|Is Required|Description|  
|----------|-----------------|-----------------|  
|IsDisplayKey|No|True or false.|  
  
## Remarks  
 This element is for reports. The element to which you apply this attribute need not be the actual table key, only an element that you will present as the key. However, the column that you use for the DisplayKey must contain unique values.  
  
## Example Tabular
  
 The following sample, in CSDLBI version 1.1, shows a column in the AdventureWorks sample data model that has been designated as the DisplayKey for the table.  
  
```xml   
<sample in progress>  
```  
  
## Example Multidimensional
  
 The following sample, in CSDLBI version 1.1, shows an excerpt from the representation of the Contoso Operations cube. In this model, the Color column has been marked as the display key for the Bikes table.  
  
```xml   
  
<EntityType   
    Name="Bike">  
.. .. ..  
<Property   
    Name="Color"   
    Type="String"   
    MaxLength="Max"   
    Unicode="true"   
    FixedLength="false">  
<bi:Property   
    ContextualNameRule="Context"   
    Alignment="Left" Units="counts"   
    SortDirection="Descending"   
    IsRightToLeft="true"   
    DefaultAggregateFunction="Max" />  
</Property>  
.. .. ..  
<bi:EntityType>  
   <bi:DisplayKey>  
      <bi:MemberRef Name="Color" />  
   </bi:DisplayKey>>  
.. .. ..  
</bi:EntityType>  
</EntityType>  
```  
  

  
  

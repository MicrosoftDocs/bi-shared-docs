---
title: "NavigationProperty Element (CSDLBI) | Microsoft Docs"
ms.date: 05/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# NavigationProperty Element (CSDLBI)

[!INCLUDE[csdl-archived](../../includes/csdl-archived.md)]

  The NavigationProperty element is a complex type that extends the CSDL Member type, to support navigation in business intelligence data models.  
  
> [!WARNING]  
>  This element is for reporting and cannot be modified or manipulated.  
  
## Elements and Attributes  
 The following table lists the elements and attributes that define the NavigationProperty element.  
  
|Name|Is Required|Description|  
|----------|-----------------|-----------------|  
|CollectionCaption|No|Plural name for referring to a set of instances of the navigation property.<br /><br /> If this attribute is omitted, the Caption attribute of the base Member is used.|  
  
## Example  
 **Tabular**  
  
 The following example shows a navigation property in CSDLBI version 1.1 that describes the link between the Product SubCategory table and the Product table in a tabular model.  
  
```xml   
  
<NavigationProperty   
    Name="Product_Sub_Category_ProductSubcategoryKey"      
    Relationship="Sandbox.Product_Product_Sub_Category_Product_Sub_Category_ProductSubcategoryKey"  
     FromRole="Product_ProductSubcategoryKey"   
    ToRole="Product_Sub_Category_ProductSubcategoryKey">  
<bi:NavigationProperty   
     ReferenceName="Product Sub-Category_ProductSubcategoryKey" />  
</NavigationProperty>  
```  
  
## Example  
 **Multidimensional**  
  
 The following example shows a navigation property in CSDLBI version 1.1 that describes the relationship between two tables in the Contoso Operations cube. The relationship connects the Bike Category table and the Product Subcategory table.  
  
```xml   
  
<NavigationProperty   
     Name="BikeSubcategory_ProductSubcategoryKey"   
     Relationship="Sandbox.Bike_BikeSubcategory_BikeSubcategory_ProductSubcategoryKey"   
     FromRole="Bike_ProductSubcategoryKey"   
     ToRole="BikeSubcategory_ProductSubcategoryKey">  
   <bi:NavigationProperty />  
</NavigationProperty>  
```  

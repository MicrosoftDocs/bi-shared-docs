---
title: "Hierarchy Element (CSDLBI) | Microsoft Docs"
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
# Hierarchy Element (CSDLBI)

  The Hierarchy element is a logical container for fields in a table that can be linked to each other to form a hierarchy. The Hierarchy element is derived from the CSDL Member element and has been extended to support the hierarchies created in business intelligence data models.  
  
## Elements and Attributes  
 The following table lists the elements and attributes that define the Hierarchy element  
  
|Name|Is Required|Description|  
|----------|-----------------|-----------------|  
|Documentation|No|A description of the hierarchy.|  
|Level|Yes|One or more Level elements that define the columns used in the hierarchy.<br /><br /> See [Level Element &#40;CSDLBI&#41;](level-element-csdlbi.md).|  
  
## Remarks  
 In tabular models, hierarchies are created by specifying parent-child relationships among columns in the same table.  
  
## Example  
 **Tabular**  
  
 The following example, in CSDLBI version 1.0, shows a hierarchy in the AdventureWorks sample model that has been added to the Products table.  
  
```xml   
  
<bi:Hierarchy Name="Categoryy">  
    <bi:Level Name="CategoryName">  
       <bi:Source>  
       <bi:PropertyRef Name="CategoryName" />  
       </bi:Source>  
    </bi:Level>  
    <bi:Level Name="ProductName">  
       <bi:Source>  
       <bi:PropertyRef Name="ProductName" />  
       </bi:Source>  
    </bi:Level>  
</bi:Hierarchy>  
  
```  
  
## Example  
 **Multidimensional**  
  
 The following example, in CSDLBI version 1.1, shows a hierarchy from the Contoso Retail Operations cube.  
  
```xml   
  
<bi:Hierarchy Name="Product_Hierarchy" Caption="Product Hierarchy" ReferenceName="Product Hierarchy">  
   <bi:Documentation>  
      <bi:Summary>DESCRIPTION_ProductModelCateg_Hierarchies</bi:Summary>  
   </bi:Documentation>  
  
   <bi:Level Name="ProductLine">  
      <bi:Source>  
      <bi:PropertyRef Name="ProductLine" />  
      </bi:Source>  
   </bi:Level>  
  
   <bi:Level Name="ModelName">  
         <bi:Source>  
      <bi:PropertyRef Name="ModelName" />  
      </bi:Source>  
   </bi:Level>  
</bi:Hierarchy>  
  
```
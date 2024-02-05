---
title: "Level Element (CSDLBI) | Microsoft Docs"
description: Learn about the elements and attributes in the Level element, a complex type that defines a single level in a hierarchy.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Level Element (CSDLBI)

[!INCLUDE[csdl-archived](../includes/csdl-archived.md)]

  The Level element is a complex type that defines a single level in a hierarchy  
  
## Elements and Attributes  
 The following table lists the elements and attributes that define the Level element.  
  
|Name|Is Required|Description|  
|----------|-----------------|-----------------|  
|Source|Yes|A container for the property reference.|  
|PropertyRef|Yes|A reference to an instance property. Other attributes of the level, such as captions, name, and reference name, can be taken from the referenced instance property. If so, you do not need to specify these in the Level element.|  
  
## Remarks  
 For more information about hierarchies in tabular models, see [Hierarchy Element &#40;CSDLBI&#41;](hierarchy-element-csdlbi.md).  
  
## Example Tabular 
  
 The following example, in CSDLBI version 1.1, shows the definition of multiple levels in a hierarchy from the AdventureWorks tabular model sample.  
  
```xml   
  
<bi:Hierarchy Name="Category">  
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
  
## Example Multidimensional  
  
 The following example, in CSDLBI version 1.1, shows a hierarchy with multiple levels, from the Contoso Operations cube.  
  
```xml   
<bi:Hierarchy   
   Name="Product_Hierarchy"   
   Caption="Product Hierarchy"   
   ReferenceName="Product Hierarchy">  
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

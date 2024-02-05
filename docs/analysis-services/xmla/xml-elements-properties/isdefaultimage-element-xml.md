---
title: "IsDefaultImage Element (XML) | Microsoft Docs"
description: Learn how the IsDefaultImage element indicates that it is possible to obtain the default image for this entity.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# IsDefaultImage Element (XML)

  Indicates that it is possible to obtain the default image for this entity by navigating this relationship to the other table and fetching the member that has the attribute, IsDefaultImage.  
  
## Syntax  
  
```xml  
  
<RelationshipEndVisualizationProperties>  
   ...  
   <IsDefaultImage>...</IsDefaultImage>  
   ...  
</RelationshipEndVisualizationProperties>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Boolean|  
|Default value|false|  
|Cardinality|0-1: Optional element that occurs once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[RelationshipEndVisualizationProperties](../../assl/data-type/relationshipendvisualizationproperties-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 For **RelationshipEndVisualizationProperties** elements, the **IsDefaultImage** element indicates that the default image for this entity can be obtained by navigating to the other end of this relationship. The default value of **false** indicates there is no default image to be obtained.  
  
  

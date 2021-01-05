---
title: "FolderPosition Element (XML) | Microsoft Docs"
description: Learn how the FolderPosition element contains information about the position of the element in a collection of elements.
ms.date: 01/05/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# FolderPosition Element (XML)

  Contains information about the position of the element in a collection of elements.  
  
## Syntax  
  
```xml  
  
<RelationshipEndVisualizationProperties>  
   ...  
   <FolderPosition>...</FolderPosition>  
   ...  
</RelationshipEndVisualizationProperties>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Integer|  
|Default value|-1|  
|Cardinality|0-1: Optional element that occurs once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[RelationshipEndVisualizationProperties](../../assl/data-type/relationshipendvisualizationproperties-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 For **RelationshipEndVisualizationProperties** elements, the **FolderPosition** element contains the position of the default folder element in a collection of folders. The default value of **false** indicates there is no default folder to be used.  
  
  

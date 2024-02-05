---
title: "IsDefaultMeasure Element (XML) | Microsoft Docs"
description: Learn how the IsDefaultMeasure element indicates that it is possible to obtain the default measure for this entity by navigating this relationship to the other table and fetching the member that has the attribute, DefaultMeasure.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# IsDefaultMeasure Element (XML)

  Indicates that it is possible to obtain the default measure for this entity by navigating this relationship to the other table and fetching the member that has the attribute, DefaultMeasure.  
  
## Syntax  
  
```xml  
  
<RelationshipEndVisualizationProperties>  
   ...  
   <IsDefaultMeasure>...</IsDefaultMeasure>  
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
 For **RelationshipEndVisualizationProperties** elements, the **IsDefaultMeasure** element indicates that it is possible to obtain the default measure for this entity by navigating to the other end of this relationship. The default value of **false** indicates there is no default measure to be obtained.  
  
  

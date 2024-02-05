---
title: "AxisInfo Element (XMLA) | Microsoft Docs"
description: Learn how the AxisInfo element represents the metadata of a single axis contained by the parent AxesInfo element.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# AxisInfo Element (XMLA)

  Represents the metadata of a single axis contained by the parent [AxesInfo](../xml-elements-properties/axesinfo-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<AxesInfo>  
   ...  
   <AxisInfo name="string">  
      <HierarchyInfo>...</HierarchyInfo>  
   </AxisInfo>  
   ...  
</AxesInfo>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|1-n: Required element that can occur more than once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[AxesInfo](../xml-elements-properties/axesinfo-element-xmla.md)|  
|Child elements|[HierarchyInfo](../xml-elements-properties/hierarchyinfo-element-xmla.md)|  
  
## Attributes  
  
|Attribute|Description|  
|---------------|-----------------|  
|Name|Required **String** attribute. The name of the axis.|  
  
## Remarks  
 In a **root** element that uses the **MDDataSet** object, an **AxisInfo** element contains a collection of **HierarchyInfo** elements that, combined with the value of the **name** attribute, represents the definition of a single axis returned in the multidimensional dataset.  
  
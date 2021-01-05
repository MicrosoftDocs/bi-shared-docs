---
title: "CellData Element (XMLA) | Microsoft Docs"
description: Learn how the CellData element contains a collection of Cell elements that represent the cell data contained by a root element that uses the MDDataSet data type.
ms.date: 01/05/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# CellData Element (XMLA)

  Contains a collection of Cell elements that represent the cell data contained by a [root](../xml-elements-properties/root-element-xmla.md) element that uses the [MDDataSet](../xml-data-types/mddataset-data-type-xmla.md) data type.  
  
## Syntax  
  
```xml  
  
<root xmlns="urn:schemas-microsoft-com:xml-analysis:mddataset">  
   ...  
   <CellData>  
      <Cell>...</Cell>  
   </CellData>  
</root>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[root](../xml-elements-properties/root-element-xmla.md)|  
|Child elements|[Cell](../xml-elements-properties/cell-element-mddataset-xmla.md)|  
  
## Remarks  
 In the parent root element, the **Axes** element is followed by the **CellData** element, a collection of **Cell** elements that contain the cell property values for each cell returned in the multidimensional dataset.  
 
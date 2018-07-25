---
title: "DataSource Element (ASSL) | Microsoft Docs"
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# DataSource Element (ASSL)

  Defines a data source in a Microsoft SQL Server Analysis Services [Database](../../../analysis-services/scripting/objects/database-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<DataSources>  
   <DataSource xsi:type="RelationalDataSource">...</DataSource>  
   <!-- or -->  
   <DataSource xsi:type="OlapDataSource">...</DataSource>  
   <!-- or -->  
   <DataSource xsi:type="PushedDataSource">...</DataSource>  
</DataSources>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[RelationalDataSource](../../../analysis-services/scripting/data-type/relationaldatasource-data-type-assl.md), [OlapDataSource](../../../analysis-services/scripting/data-type/olapdatasource-data-type-assl.md), [PushedDataSource](../../../analysis-services/scripting/data-type/pusheddatasource-data-type-assl.md)|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[DataSources](../../../analysis-services/scripting/collections/datasources-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.DataSource>.  
  
## See Also  
 [Database Element &#40;ASSL&#41;](../../../analysis-services/scripting/objects/database-element-assl.md)   
 [Objects &#40;ASSL&#41;](../../../analysis-services/scripting/objects/objects-assl.md)  
  
  

---
title: "Execute Method (XMLA) | Microsoft Docs"
description: Learn how the Execute method sends XML for Analysis (XMLA) commands to an instance of Analysis Services.
ms.date: 01/05/2021
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis
---
# XML Elements - Methods - Execute

  Sends XML for Analysis (XMLA) commands to an instance of Analysis Services. This includes requests involving data transfer, such as retrieving or updating data on the server.  
  
 **Namespace** urn:schemas-microsoft-com:xml-analysis  
  
 **SOAP Action** "urn:schemas-microsoft-com:xml-analysis:Execute"  
  
## Syntax  
  
```xml  
  
<Execute>  
   <Command>...</Command>  
   <Properties>...</Properties>  
   <Parameters>...</Parameters>  
</Execute>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that occurs once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|None|  
|Child elements|[Command](xml-elements-properties/command-element-xmla.md), [Parameters](xml-elements-properties/parameters-element-xmla.md), [Properties](xml-elements-properties/properties-element-xmla.md)|  
  
## Remarks

 The **Execute** method executes XMLA commands provided in the **Command** element and returns any resulting data using either the XMLA [Rowset](xml-data-types/rowset-data-type-xmla.md) data type (for tabular result sets) or the XMLA [MDDataSet](xml-data-types/mddataset-data-type-xmla.md) data type (for multidimensional result sets.)  
  
## Example

 The following code sample is an example of an **Execute** method call that contains an Multidimensional Expressions (MDX) SELECT statement.  
  
```xml  
<Execute xmlns="urn:schemas-microsoft-com:xml-analysis">  
   <Command>  
      <Statement>  
         SELECT [Measures].MEMBERS ON COLUMNS FROM [Adventure Works]  
      </Statement>  
   </Command>  
   <Properties>  
      <PropertyList>  
         <DataSourceInfo>Provider=MSOLAP;Data Source=local;</DataSourceInfo>  
         <Catalog>Adventure Works DW Multidimensional 2012</Catalog>  
         <Format>Multidimensional</Format>  
         <AxisFormat>ClusterFormat</AxisFormat>  
      </PropertyList>  
   </Properties>  
</Execute>  
```
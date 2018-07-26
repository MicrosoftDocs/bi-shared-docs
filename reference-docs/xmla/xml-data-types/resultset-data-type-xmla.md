---
title: "Resultset Data Type (XMLA) | Microsoft Docs"
ms.date: 07/24/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Resultset Data Type (XMLA)

  Defines an abstract primitive data type that represents data returned from a [Discover](../xml-elements-methods-discover.md) or [Execute](../xml-elements-methods-execute.md) method call.  
  
 **Namespace** urn:schemas-microsoft-com:xml-analysis:resultset  
  
## Syntax  
  
```xml  
  
<Resultset>  
   <Exception>...</Exception>  
   <Messages>...</Messages>  
</Resultset>  
```  
  
## Data type characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|None|  
|Derived data types|[MDDataSet](../xml-data-types/mddataset-data-type-xmla.md), [olapxmla_EmptyResult](../xml-data-types/emptyresult-data-type-xmla.md), [Rowset](../xml-data-types/rowset-data-type-xmla.md)|  
  
## Data type relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[Exception](../xml-elements-properties/exception-element-xmla.md), [Messages](../xml-elements-properties/messages-element-xmla.md)|  
|Derived elements|None|  
  
## Remarks  
 The **Resultset** data type is a self-describing XML result set that can include both schema and data, depending on the type of information to be returned.  

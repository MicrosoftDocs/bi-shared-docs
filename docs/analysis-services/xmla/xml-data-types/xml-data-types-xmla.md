---
title: "XML Data Types (XMLA) | Microsoft Docs"
description: Learn about the supported XML data types used by XML for Analysis (XMLA).
ms.date: 01/05/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# XML Data Types (XMLA)

  In addition to the standard primitive and derived types defined by the XML 1.0 recommendation, the XML for Analysis (XMLA) 1.1 specification defines additional data types to support the representation of multidimensional and tabular data.  
  
 XMLA uses the data types listed in the following table.  
  
|Data types|Description|  
|----------------|-----------------|  
|Boolean|The standard XML **boolean** data type.|  
|Decimal|The standard XML **decimal** data type.|  
|[EmptyResult](../xml-data-types/emptyresult-data-type-xmla.md)|A namespace on the **root** element. This namespace is returned when an XMLA command does not return a result because either the XMLA command does not normally return a result or because an error occurred on the Analysis Services instance while executing the XMLA command.|  
|[EnumString](../xml-data-types/enumstring-data-type-xmla.md)|A set of named string constants for a given enumerator.|  
|Integer|The standard XML **int** data type.|  
|[MDDataSet](../xml-data-types/mddataset-data-type-xmla.md)|Multidimensional data returned by the *Result* parameter of the [Execute](../xml-elements-methods-execute.md) method.|  
|[Resultset](../xml-data-types/resultset-data-type-xmla.md)|A self-describing XML result set returned by the **Execute** method.|  
|[Rowset](../xml-data-types/rowset-data-type-xmla.md)|Rows from a data source, structured by an embedded XML schema, returned by the [Discover](../xml-elements-methods-discover.md) method.|  
|String|The XML **string** data type.|  
|UnsignedInt|The XML **unsignedInt** schema type.|  
  
 For complete descriptions of the standard XML data types, see the World Wide Web Consortium (WC3) candidate recommendation.
---
title: "row Element (XMLA) | Microsoft Docs"
description: Learn how the row element contains a single row of data for a root element that contains tabular data returned by a Discover or Execute method call.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# row Element (XMLA)

  Contains a single row of data for a [root](../xml-elements-properties/root-element-xmla.md) element that contains tabular data returned by a [Discover](../xml-elements-methods-discover.md) or [Execute](../xml-elements-methods-execute.md) method call.  
  
## Syntax  
  
```xml  
  
<root xmlns="urn:schemas-microsoft-com:xml-analysis:rowset">  
   <row>  
      <!-- One or more column elements -->  
   </row>  
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
|Parent elements|[root](../xml-elements-properties/root-element-xmla.md) (using the [Rowset](../xml-data-types/rowset-data-type-xmla.md) data type)|  
|Child elements|One or more column elements.|  
  
## Remarks  
 Each row returned by a **root** element that contains tabular data has a corresponding **row** element. Each column in the **root** element is represented by a separate XML element. The value of the column for the **row** element is the data contained by the XML element, and the name of the column corresponds to the name of the XML element.  
  
 There are two ways to express a null value for a column within a row:  
  
-   A missing column element implies that the column is null.  
  
-   The column element may use the `xsi:nil='true'` attribute to indicate that it has a null value.  
  
 For example, if a row has a single column called, Store_Name, and its value is NULL, it can be represented as either:  
  
```xml  
<row>  
</row>  
```  
  
 Or:  
  
```xml  
<row>  
   <Store_name xsi:nil='true'/>  
</row>  
```  
  
 If a column element contains an error, an **Error** element provides information about an error, as described in the following example:  
  
```xml  
<row>   <Store_name>  
      <Error xmlns="urn:schemas-microsoft-com:xml-analysis:exception">  
         <ErrorCode>3238658054</ErrorCode>  
         <Description>The object [X] was not found in the cube when [X] was parsed.</Description>  
      </Error>  
   </Store_name>  
</row>  
```
---
title: "Properties Element (XMLA) | Microsoft Docs"
description: Learn how the Properties element contains XML for Analysis (XMAL) properties used by the Discover and Execute methods.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Properties Element (XMLA)

  Contains XML for Analysis (XMAL) properties used by the [Discover](../xml-elements-methods-discover.md) and [Execute](../xml-elements-methods-execute.md) methods.  
  
## Syntax  
  
```xml  
  
<Discover> <!-- or Execute -->  
...  
   <Properties>  
      <PropertyList>...</PropertyList>  
   </Properties>  
...  
</Discover>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Discover](../xml-elements-methods-discover.md), [Execute](../xml-elements-methods-execute.md)|  
|Child elements|[PropertyList](../xml-elements-properties/propertylist-element-xmla.md)|  
  
## Remarks  
 The **Properties** element represents XMLA properties used to control aspects of the **Discover** and **Execute** methods, such as defining the information required to connect to the data source, specifying the return format of the result set, or specifying the locale in which the data should be formatted.  
  
 The available properties and their values can be obtained by using the DISCOVER_PROPERTIES request type with the **Discover** method.  
  
## Example  
  
```xml  
<Properties>  
   <PropertyList>  
      <DataSourceInfo>  
         Provider=MSOLAP;Data Source=local;  
      </DataSourceInfo>  
      <Catalog>  
         Foodmart 2000  
      </Catalog>  
      <Format>  
         Multidimensional  
      </Format>  
   </PropertyList>  
</Properties>  
```  
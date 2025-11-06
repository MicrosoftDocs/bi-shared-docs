---
title: "PropertyList Element (XMLA) | Microsoft Docs"
description: Learn how the PropertyList element contains a collection of XML for Analysis (XMLA) properties used by the Discover and Execute methods.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference

---
# PropertyList Element (XMLA)

  Contains a collection of XML for Analysis (XMLA) properties used by the [Discover](../xml-elements-methods-discover.md) and [Execute](../xml-elements-methods-execute.md) methods.  
  
## Syntax  
  
```xml  
  
<Properties>  
   <PropertyList>  
      <!-- Zero or more XMLA properties -->  
   </PropertyList>  
</Properties>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Properties](../xml-elements-properties/properties-element-xmla.md)|  
|Child elements|XMLA properties (see Remarks)|  
  
## Remarks  
 The **PropertyList** element contains a collection of XMLA properties. Each property allows the user to control some aspect of the **Discover** or **Execute** method, such as defining the information required to connect to the data source, specifying the return format of the result set, or specifying the locale in which the data should be formatted. Each XMLA property in the **PropertyList** element is defined by a separate XML element. The value of the XMLA property is the data contained by the XML element, and the name of the XMLA property corresponds to the name of the XML element.  
  
 The available properties and their values can be obtained by using the DISCOVER_PROPERTIES request type with the **Discover** method. There is no required order for the properties listed in the **PropertyList** element.  
  
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
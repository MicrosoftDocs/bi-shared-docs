---
title: "Restrictions Element (XMLA) | Microsoft Docs"
description: Learn how the Restrictions element contains restriction columns and data used by the Discover method.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
---

# Restrictions Element (XMLA)

  Contains restriction columns and data used by the [Discover](../xml-elements-methods-discover.md) method.  
  
## Syntax  
  
```xml  
  
<Discover>  
...  
   <Restrictions>  
      <RestrictionList>...</RestrictionList>  
   </Restrictions>  
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
|Parent elements|[Discover](../xml-elements-methods-discover.md)|  
|Child elements|[RestrictionList](../xml-elements-properties/restrictionlist-element-xmla.md)|  
  
## Remarks  
 The **Restrictions** element represents restriction columns and data used to restrict the information retrieved by the **Discover** method.  
  
## Example  
  
```xml  
<Discover xmlns="urn:schemas-microsoft-com:xml-analysis">  
   <RequestType>DISCOVER_PROPERTIES</RequestType>  
   <Restrictions>  
      <RestrictionList xmlns="urn:schemas-microsoft-com:xml-analysis">  
         <PropertyName>Catalog</PropertyName>  
      </RestrictionList>  
   </Restrictions>  
   <Properties />  
</Discover>  
```  

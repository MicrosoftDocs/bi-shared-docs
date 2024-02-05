---
title: "RestrictionList Element (XMLA) | Microsoft Docs"
description: Learn how the RestrictionList element contains a collection of restriction columns and values used by the Discover method.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# RestrictionList Element (XMLA)

  Contains a collection of restriction columns and values used by the [Discover](../xml-elements-methods-discover.md) method.  
  
## Syntax  
  
```xml  
  
<Restrictions>  
   <RestrictionList>  
      <!-- Zero or more restriction columns and values -->  
   </RestrictionList>  
</Restrictions>  
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
|Parent elements|[Restrictions](../xml-elements-properties/restrictions-element-xmla.md)|  
|Child elements|Restriction columns and values (see Remarks).|  
  
## Remarks  
 The **RestrictionList** element contains a collection of restriction columns on which the data returned by the **Discover** method can be filtered. Each restriction column in the **RestrictionList** element is defined by a separate XML element. The value of the restriction column is the data contained by the XML element, and the name of the restriction column corresponds to the name of the XML element.  

  

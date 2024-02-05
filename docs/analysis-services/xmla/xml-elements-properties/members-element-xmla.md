---
title: "Members Element (XMLA) | Microsoft Docs"
description: Learn how the Members element contains a collection of Member elements contained by the parent CrossProduct element.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Members Element (XMLA)

  Contains a collection of [Member](../xml-elements-properties/member-element-xmla.md) elements contained by the parent [CrossProduct](../xml-elements-properties/crossproduct-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<CrossProduct>  
   <Members Hierarchy="string">  
      <Member>...</Member>  
   </Members>  
   ...  
</CrossProduct>  
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
|Parent elements|[CrossProduct](../xml-elements-properties/crossproduct-element-xmla.md)|  
|Child elements|[Member](../xml-elements-properties/member-element-xmla.md)|  
  
## Attributes  
  
|Attribute|Description|  
|---------------|-----------------|  
|Hierarchy|Required **String** attribute. The name of the hierarchy to which the members contained by the **Members** element belong.|  
  
## Remarks  
 When a client application sets the **AxisFormat** property to *ClusterFormat*, the members on each axis are divided into clusters in which each cluster represents a cross-product between ordered sets of members from each hierarchy. Each **Axis** element consists of one or more **CrossProduct** elements. Every **CrossProduct** element contains a **Members** element for each hierarchy on the axis. The **Members** element, in turn, contains one **Member** element for each member of the specified hierarchy included in the cross-product.  
  
## Example  
 The following example illustrates the structure of the **Members** element when a client specifies *ClusterFormat* for the **AxisFormat** XMLA property, given the following members for the axis:  

:::row:::
    :::column:::
        **Time** hierarchy

        **Category** hierarchy

        Clusters
    :::column-end:::
    :::column:::
        1999

        Actual

        Clusters 1
    :::column-end:::
    :::column:::
        1999

        Budget

        Clusters 1
    :::column-end:::
    :::column:::
        2000

        Budget

        Clusters 1
    :::column-end:::
    :::column:::
        2001

        Budget

        Clusters 2
    :::column-end:::
:::row-end:::

```xml  
<Axes>  
   <Axis name="Axis0">  
      <CrossProduct Size = "4">  
         <Members Hierarchy="Time">  
            <Member>  
               <UName>[Time].[1999]</UName>  
               ...  
            </Member>  
            <Member>  
               <UName>[Time].[2000]</UName>  
               ...  
            </Member>  
         </Members>  
         <Members Hierarchy="Category">  
            <Member>  
               <UName>[Scenario].[Actual]</UName>  
               ...  
            </Member>  
            <Member>  
               <UName>[Scenario].[Budget]</UName>  
               ...  
            </Member>  
         </Members>  
      </CrossProduct>  
      <CrossProduct Size = "1">  
         <Members Hierarchy="Time">  
            <Member>  
               <UName>[Time].[2001]</UName>  
               ...  
            </Member>  
         </Members>  
         <Members Hierarchy="Category">  
            <Member>  
               <UName>[Scenario].[Budget]</UName>  
               ...  
            </Member>  
         </Members>  
      </CrossProduct>  
   </Axis>  
   ...  
</Axes>  
```  

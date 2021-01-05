---
title: "CrossProduct Element (XMLA) | Microsoft Docs"
description: Learn how the CrossProduct element contains a cross-product between ordered sets of members from each hierarchy for an Axis element that uses the MDDataSet data type, returned by the Execute method.
ms.date: 01/05/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# CrossProduct Element (XMLA)

  Contains a cross-product between ordered sets of members from each hierarchy for an [Axis](../xml-elements-properties/axis-element-xmla.md) element that uses the [MDDataSet](../xml-data-types/mddataset-data-type-xmla.md) data type, returned by the [Execute](../xml-elements-methods-execute.md) method.  
  
## Syntax  
  
```xml  
  
<Axis>  
   ...  
   <CrossProduct Size="integer">  
      <Members>...</Members>  
   </CrossProduct>  
   ...  
</Axis>  
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
|Parent elements|[Axis](../xml-elements-properties/axis-element-xmla.md)|  
|Child elements|[Members](../xml-elements-properties/members-element-xmla.md)|  
  
## Attributes  
  
|Attribute|Description|  
|---------------|-----------------|  
|Size|Required **Integer** attribute. Indicates the number of tuples contained in the cross-product represented by the **CrossProduct** element.|  
  
## Remarks  
 When a client application sets the **AxisFormat** property to *ClusterFormat*, the members on each axis are divided into clusters in which each cluster represents a cross-product between ordered sets of members from each hierarchy. Each cluster is represented by a **CrossProduct** element. Every **CrossProduct** element contains a **Members** element for each hierarchy on the axis. A **CrossProduct** element can contain members from a single hierarchy.  
  
## Example  
 The following example illustrates the structure of the **CrossProduct** element when a client specifies *ClusterFormat* for the **AxisFormat** XMLA property, given the following members for the axis:  

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
      <CrossProduct Size="4">  
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
      <CrossProduct Size="1">  
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
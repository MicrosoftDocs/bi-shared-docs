---
title: "Axis Element (XMLA) | Microsoft Docs"
description: Learn how the Axis element contains a set of tuples used to represent a single axis in a multidimensional dataset contained by an Axes element that uses the MDDataSet data type, returned by the Execute method.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Axis Element (XMLA)

  Contains a set of tuples used to represent a single axis in a multidimensional dataset contained by an [Axes](../xml-elements-properties/axes-element-xmla.md) element that uses the [MDDataSet](../xml-data-types/mddataset-data-type-xmla.md) data type, returned by the [Execute](../xml-elements-methods-execute.md) method.  
  
## Syntax  
  
```xml  
  
<Axes>  
   ...  
   <Axis> <!-- when AxisFormat XMLA property is set to ClusterFormat -->  
      <CrossProduct>...</CrossProduct>  
   </Axis>  
   <Axis> <!-- when AxisFormat XMLA property is set to TupleFormat or CustomFormat -->  
      <Tuples>...</Tuples>  
   </Axis>  
   ...  
</Axes>  
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
|Parent elements|[Axes](../xml-elements-properties/axes-element-xmla.md)|  
|Child elements|[CrossProduct](../xml-elements-properties/crossproduct-element-xmla.md) or [Tuples](../xml-elements-properties/tuples-element-xmla.md)|  
  
## Remarks  
 The content of the **Axis** element varies depending on the value of the **AxisFormat** XMLA property used by the **Execute** method.  
  
## TupleFormat  
 When a client application sets the **AxisFormat** property to *TupleFormat*, an axis is represented as a set of tuples. Each **Axis** element contains a **Tuples** element that represents the set of tuples on that axis. Each tuple is represented by using a **Tuple** element that contains **Member** elements from every hierarchy on the axis.  
  
## ClusterFormat  
 When a client application sets the **AxisFormat** property to *ClusterFormat*, the members on each axis are divided into clusters in which each cluster represents a cross-product between ordered sets of members from each hierarchy. Each **Axis** element consists of one or more **CrossProduct** elements. Every **CrossProduct** element contains a **Members** element for each hierarchy on the axis.  
  
## CustomFormat  
 When a client application sets the **AxisFormat** property to *CustomFormat*, the value is treated the same as the *TupleFormat* value by an Analysis Services instance.  
  
## Examples  
  
### Description  
 The following example illustrates the structure of the **Axis** elements when a client specifies *TupleFormat* or *CustomFormat* for the **AxisFormat** XMLA property, given the following members for the axis:  

:::row:::
    :::column:::
        **Time** hierarchy

        **Category** hierarchy
    :::column-end:::
    :::column:::
        1999

        Actual
    :::column-end:::
    :::column:::
        1999

        Budget
    :::column-end:::
    :::column:::
        2000

        Budget
    :::column-end:::
:::row-end:::

### Code  
  
```xml  
<Axes>  
   <Axis name="Axis0">  
      <Tuples>  
         <Tuple>  
            <Member Hierarchy="Time">  
               <UName>[Time].[1999]</UName>  
               ...  
            </Member>  
            <Member Hierarchy="Category">  
               <UName>[Scenario].[Actual]</UName>  
               ...  
            </Member>  
         </Tuple>  
         <Tuple>  
            <Member Hierarchy="Time">  
               <UName>[Time].[1999]</UName>  
               ...  
            </Member>  
            <Member Hierarchy="Category">  
               <UName>[Scenario].[Budget]</UName>  
               ...  
            </Member>  
         </Tuple>  
         <Tuple>  
            <Member Hierarchy="Time">  
               <UName>[Time].[2000]</UName>  
               ...  
            </Member>  
            <Member Hierarchy="Category">  
               <UName>[Scenario].[Budget]</UName>  
               ...  
            </Member>  
         </Tuple>  
      </Tuples>  
   </Axis>  
   ...  
</Axes>  
```  
  
### Description  
 The following example illustrates the structure of the **Axis** elements when a client specifies *ClusterFormat* for the **AxisFormat** XMLA property, given the following members for the axis:  

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
  
### Code  
  
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
  
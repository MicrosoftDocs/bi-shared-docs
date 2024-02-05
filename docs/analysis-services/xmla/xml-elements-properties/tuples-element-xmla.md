---
title: "Tuples Element (XMLA) | Microsoft Docs"
description: Learn how the Tuples element contains a set of Tuple objects for an Axis element that uses the MDDataSet data type, returned by the Execute method.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Tuples Element (XMLA)

  Contains a set of [Tuple](../xml-elements-properties/tuple-element-xmla.md) objects for an [Axis](../xml-elements-properties/axis-element-xmla.md) element that uses the [MDDataSet](../xml-data-types/mddataset-data-type-xmla.md) data type, returned by the [Execute](../xml-elements-methods-execute.md) method.  
  
## Syntax  
  
```xml  
  
<Axis>  
   ...  
   <Tuples>  
      <Tuple>...</Tuple>  
   </Tuples>  
   ...  
</Axis>  
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
|Parent elements|[Axis](../xml-elements-properties/axis-element-xmla.md)|  
|Child elements|[Tuple](../xml-elements-properties/tuple-element-xmla.md)|  
  
## Remarks  
 When a client application sets the **AxisFormat** property to *TupleFormat*, an axis is represented as a set of tuples. Each **Axis** element contains a **Tuples** element representing the set of tuples on that axis. Each tuple is represented by using a **Tuple** element that contains [Member](../xml-elements-properties/member-element-xmla.md) elements from every hierarchy on the axis.  
  
## Example  
 The following example illustrates the structure of the **Tuples** element when a client specifies *TupleFormat* or *CustomFormat* for the **AxisFormat** XML for Analysis (XMLA) property, given the following members for the axis:  
  
**Time** hierarchy, 1999, 1999, 2000  
**Category** hierarchy, Actual, Budget, Budget  
  
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

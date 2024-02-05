---
title: "Axes Element (XMLA) | Microsoft Docs"
description: Learn how the Axes element contains a collection of Axis elements representing axis data contained by a root element that uses the MDDataSet data type.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Axes Element (XMLA)

  Contains a collection of [Axis](../xml-elements-properties/axis-element-xmla.md) elements representing axis data contained by a [root](../xml-elements-properties/root-element-xmla.md) element that uses the [MDDataSet](../xml-data-types/mddataset-data-type-xmla.md) data type.  
  
## Syntax  
  
```xml  
  
<root xmlns="urn:schemas-microsoft-com:xml-analysis:mddataset">  
   ...  
   <Axes>  
      <Axis>...</Axis>  
   </Axes>  
   ...  
</root>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Any|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[root](../xml-elements-properties/root-element-xmla.md)|  
|Child elements|[Axis](../xml-elements-properties/axis-element-xmla.md)|  
  
## Remarks  
 Under the **Axes** element, the **Axis** elements are listed in the order that they occur in the dataset, starting at zero. The **AxisFormat** XMLA property setting determines how **Axis** elements are formatted. For more information about the **AxisFormat** property, see [Supported XMLA Properties &#40;XMLA&#41;](../xml-elements-properties/propertylist-element-supported-xmla-properties.md).  
  
 An axis represents a set of tuples, in which all tuples in the set have the same dimensionality. A set can be represented in different ways with different advantages. For example, the following set of four tuples can be represented as a collection of two-dimensional tuples or a Cartesian product of two one-dimensional sets.  
  
|1999|1999|2000|2000|  
|----------|----------|----------|----------|  
|Actual|Budget|Actual|Budget|  
  
 This set of tuples can be represented either as a collection of two-dimensional tuples:  
  
```xml  
{ ( 1999, Actual ), ( 1999, Budget ), ( 2000, Actual ), ( 2000, Budget ) }  
```  
  
 This set can also be represented as a Cartesian product of two one-dimensional sets:  
  
```xml  
{ 1999, 2000 } x { Actual, Budget }  
```  
  
 The first representation, two-dimensional tuples, is simpler for client tools to use. The second representation, a Cartesian product of one-dimensional sets, uses less space and preserves the multidimensional nature of the set.  
  
 The following table lists operations that can be used to define and characterize the structure and members of an axis.  
  
|Operation|Description|  
|---------------|-----------------|  
|Member|The smallest unit of an axis representing the member of a dimension hierarchy.|  
|Members|A collection of **Member** objects from the same dimension hierarchy.|  
|Tuple|A collection of members from different dimension hierarchies.|  
|Tuples|A collection of **Tuple** objects with the same dimensionality.|  
|Union|A union of sets.|  
|CrossJoin|A Cartesian product of sets.|  
  
 These operations translate the two-dimensional tuples and the Cartesian product of one-dimensional sets as follows.  
  
## Two-dimensional tuples  
  
```xml  
Tuples (  
   Tuple( Member(1999), Member(Actual) ),  
   Tuple( Member(1999), Member(Budget) ),  
   Tuple( Member(2000), Member(Actual) ),  
   Tuple( Member(2000), Member(Budget) )  
```  
  
## Cartesian product of one-dimensional sets  
  
```xml  
CrossProduct (  
   Members( Member(1999), Member(2000) ),  
   Members( Member(Actual), Member(Budget) )  
```  
  
 A client can use the **AxisFormat** property to request a specific representation.  

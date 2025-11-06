---
title: "DeleteWithDescendants Element (XMLA) | Microsoft Docs"
description: Learn how the DeleteWithDescendants element indicates whether the descendants of attribute members are also deleted by the parent Drop command.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference

---
# DeleteWithDescendants Element (XMLA)

  Indicates whether the descendants of attribute members are also deleted by the parent [Drop](../xml-elements-commands/drop-element-xmla.md) command.  
  
## Syntax  
  
```xml  
  
<Drop>  
   ...  
   <DeleteWithDescendants>...</DeleteWithDescendants>  
   ...  
</Drop>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Boolean|  
|Default value|False|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Drop](../xml-elements-commands/drop-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **DeleteWithDescendants** element determines whether the **Drop** command should delete the attribute members identified by the [Where](../xml-elements-properties/where-element-xmla.md) element, but also that the descendants of those attribute members are to be dropped as well.  
  
> [!NOTE]  
>  This element applies only to attribute members in parent-child hierarchies.  


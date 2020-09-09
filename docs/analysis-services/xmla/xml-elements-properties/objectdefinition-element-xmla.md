---
title: "ObjectDefinition Element (XMLA) | Microsoft Docs"
description: Learn how the ObjectDefinition element contains one or more Analysis Services Scripting Language (ASSL) elements, used to create or alter objects on an instance of Analysis Services.
ms.date: 07/24/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# ObjectDefinition Element (XMLA)

  Contains one or more Analysis Services Scripting Language (ASSL) elements, used to create or alter objects on an instance of Analysis Services.  
  
## Syntax  
  
```xml  
  
<Create> <!-- or Alter -->  
   ...  
   <ObjectDefinition>  
      <!-- One or more ASSL elements -->  
   </ObjectDefinition>  
   ...  
</Create>  
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
|Parent elements|[Alter](../xml-elements-commands/alter-element-xmla.md), [Create](../xml-elements-commands/create-element-xmla.md)|  
|Child elements|Required ASSL elements. One or more ASSL elements, used to define Analysis Services objects. For more information about ASSL, see [Properties &#40;XMLA&#41;](../xml-elements-properties/xml-elements-properties.md).|  
  
## Remarks  
  
## Example  
 The following example creates an empty database named **Test Database** on an Analysis Services instance.  
  
```xml  
  
      <Create xmlns="http://schemas.microsoft.com/analysisservices/2003/engine">  
   <ObjectDefinition>  
      <Database xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
         <Name>Test Database</Name>  
         <Description>A test database.</Description>  
      </Database>  
   </ObjectDefinition>  
</Create>  
```  
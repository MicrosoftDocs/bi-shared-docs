---
title: "Create Element (XMLA) | Microsoft Docs"
description: Learn how the Create element contains Analysis Services Scripting Language (ASSL) elements used by the **Execute** method to create objects on a Analysis Services instance.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Create Element (XMLA)

  Contains Analysis Services Scripting Language (ASSL) elements used by the **Execute** method to create objects on a Analysis Services instance.  
  
## Syntax  
  
```xml  
  
<Command>  
   <Create Scope="enum" AllowOverwrite="boolean">  
      <ParentObject>...</ParentObject>  
      <ObjectDefinition>...</ObjectDefinition>  
   </Create>  
</Command>  
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
|Parent elements|[Command](../xml-elements-properties/command-element-xmla.md)|  
|Child elements|[ObjectDefinition](../xml-elements-properties/objectdefinition-element-xmla.md), [ParentObject](../xml-elements-properties/parentobject-element-xmla.md)|  
  
## Attributes  
  
|Attribute|Description|  
|---------------|-----------------|  
|AllowOverwrite|Optional **Boolean** attribute. If set to True, the objects defined in the **ObjectDefinition** element can overwrite existing objects on the Analysis Services instance. If this attribute is omitted or set to False, the presence of an existing object generates an error.|  
|Scope|Optional **Enum** attribute. Defines the duration of objects defined in the **ObjectDefinition** element. If this attribute is omitted, the objects defined in the **ObjectDefinition** element are persisted on the Analysis Services instance. The following value is available:<br /><br /> *Session*: The objects defined in the **ObjectDefinition** element exist only for the duration of the XML for Analysis (XMLA) session.<br />                  Note that when using the *Session* setting, the **ObjectDefinition** element can only contain [Dimension](../../assl/objects/dimension-element-assl.md), [Cube](../../assl/objects/cube-element-assl.md), or [MiningModel](../../assl/objects/miningmodel-element-assl.md) ASSL elements.|  
  
## Remarks  
 Each **Create** operation creates one major object under a parent given by the **ParentObject** element. If the parent object is omitted, it is assumed to be the destination Analysis Services instance. This generates an error if the parent of a major object is not the destination instance.  
  
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
---
title: "Alter Element (XMLA) | Microsoft Docs"
description: Learn how the Alter element contains Analysis Services Scripting Language (ASSL) elements used by the Execute method to alter objects on an instance of Analysis Services.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Alter Element (XMLA)

  Contains Analysis Services Scripting Language (ASSL) elements used by the [Execute](../xml-elements-methods-execute.md) method to alter objects on an instance of Analysis Services.  
  
## Syntax  
  
```xml  
  
<Command>  
   <Alter Scope="enum" AllowCreate="boolean" ObjectExpansion="enum">  
      <Object>...</Object>  
      <ObjectDefinition>...</ObjectDefinition>  
   </Alter>  
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
|Child elements|[Object](../xml-elements-properties/object-element-xmla.md), [ObjectDefinition](../xml-elements-properties/objectdefinition-element-xmla.md)|  
  
## Attributes  
  
|Attribute|Description|  
|---------------|-----------------|  
|AllowCreate|(Optional **Boolean** attribute) Indicates whether objects defined in the **Alter** command should be created if they do not already exist.<br /><br /> If set to true, the objects defined in the **ObjectDefinition** element are created on the Analysis Services instance if they do not already exist. In other words, the **Alter** command is treated as a **Create** command if the objects do not already exist on the instance.<br /><br /> If this attribute is omitted or set to **false**, an error occurs if the objects do not already exist.|  
|ObjectExpansion|(Optional **Enum** attribute) Defines the extent of alteration to be performed by the **Execute** method.<br /><br /> If set to *ObjectProperties*, the **ObjectDefinition** element should contain only the complete definition of the major object to be altered, including subordinate minor objects. Subordinate major objects of the object to be altered remain unchanged.<br /><br /> Note: When using the *ObjectProperties* setting with the [ClrAssembly](../../assl/data-type/clrassembly-data-type-assl.md) data type, the [Data](../../assl/objects/data-element-assl.md) element of the associated [ClrAssemblyFile](../../assl/data-type/clrassemblyfile-data-type-assl.md) data types does not need to be specified. If not specified, the **ClrAssembly** uses existing files.<br /><br /> If set to *ExpandFull*, the **ObjectDefinition** element should contain not just the definition of the object to be altered, but also the definitions of all major objects which are descendants of the object to be altered.<br /><br /> Note: The *ExpandFull* setting cannot be used with the [Server](../../assl/objects/server-element-assl.md) element.|  
|Scope|(Optional **Enum** attribute) Defines the duration of objects defined in the **ObjectDefinition** element.<br /><br /> If set to *Session*, the objects defined in the **ObjectDefinition** element exist only for the duration of the XMLA session.<br /><br /> Note: When using the *Session* setting, the **ObjectDefinition** element can only contain [Dimension](../../assl/objects/dimension-element-assl.md), [Cube](../../assl/objects/cube-element-assl.md), or [MiningModel](../../assl/objects/miningmodel-element-assl.md) ASSL elements.<br /><br /> If this attribute is omitted, the objects defined in the **ObjectDefinition** element are persisted on the Analysis Services instance.|  
  
## Remarks  
 Each **Alter** command changes the definition of one major object under the parent object specified by the [ParentObject](../xml-elements-properties/parentobject-element-xmla.md) element.
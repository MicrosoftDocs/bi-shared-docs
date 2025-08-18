---
title: "Creating and Altering Objects (XMLA) | Microsoft Docs"
description: Learn how to create and alter major objects by using the CREATE and ALTER command, respectively.
ms.date: 05/02/2018
ms.service: analysis-services
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis
ms.custom:
  - xmla
  - sfi-ropc-nochange

---
# Creating and Altering Objects (XMLA)
  Major objects can be independently created, altered, and deleted. Major objects include the following objects:  
  
-   Servers  
  
-   Databases  
  
-   Dimensions  
  
-   Cubes  
  
-   Measure groups  
  
-   Partitions  
  
-   Perspectives  
  
-   Mining models  
  
-   Roles  
  
-   Commands associated with a server or database  
  
-   Data sources  
  
 You use the [Create](../xmla/xml-elements-commands/create-element-xmla.md) command to create a major object on an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], and the [Alter](../xmla/xml-elements-commands/alter-element-xmla.md) command to alter an existing major object on an instance. Both commands are run using the [Execute](../xmla/xml-elements-methods-execute.md) method.  
  
## Creating Objects  
 When you create objects by using the **Create** method, you must first identify the parent object that contains the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object to be created. You identify the parent object by providing an object reference in the [ParentObject](../xmla/xml-elements-properties/object-element-xmla.md) property of the **Create** command. Each object reference contains the object identifiers needed to uniquely identify the parent object for the **Create** command. For more information about object references, see [Defining and Identifying Objects &#40;XMLA&#41;](../../analysis-services/multidimensional-models-scripting-language-assl-xmla/defining-and-identifying-objects-xmla.md).  
  
 For example, you must provide an object reference to a cube to create a new measure group for the cube. The object reference for the cube in the **ParentObject** property contains both a database identifier and a cube identifier, as the same cube identifier could potentially be used on a different database.  
  
 The [ObjectDefinition](../xmla/xml-elements-properties/objectdefinition-element-xmla.md) element contains Analysis Services Scripting Language (ASSL) elements that define the major object to be created. For more information about ASSL, see [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../../analysis-services/multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).  
  
 If you set the **AllowOverwrite** attribute of the **Create** command to true, you can overwrite an existing major object that has the specified identifier. Otherwise, an error occurs if a major object that has the specified identifier already exists in the parent object.  
  
 For more information about the **Create** command, see [Create Element &#40;XMLA&#41;](../xmla/xml-elements-commands/create-element-xmla.md).  
  
### Creating Session Objects  
 Session objects are temporary objects that are available only to the explicit or implicit session used by a client application and are deleted when the session is ended. You can create session objects by setting the **Scope** attribute of the **Create** command to *Session*.  
  
> [!NOTE]  
>  When using the *Session* setting, the **ObjectDefinition** element can only contain [Dimension](../assl/objects/dimension-element-assl.md), [Cube](../assl/objects/cube-element-assl.md), or [MiningModel](../assl/objects/miningmodel-element-assl.md) ASSL elements.  
  
## Altering Objects  
 When modifying objects by using the **Alter** method, you must first identify the object to be modified by providing an object reference in the [Object](../xmla/xml-elements-properties/object-element-xmla.md) property of the **Alter** command. Each object reference contains the object identifiers needed to uniquely identify the object for the **Alter** command. For more information about object references, see [Defining and Identifying Objects &#40;XMLA&#41;](../../analysis-services/multidimensional-models-scripting-language-assl-xmla/defining-and-identifying-objects-xmla.md).  
  
 For example, you must provide an object reference to a cube in order to modify the structure of a cube. The object reference for the cube in the **Object** property contains both a database identifier and a cube identifier, as the same cube identifier could potentially be used on a different database.  
  
 The **ObjectDefinition** element contains ASSL elements that define the major object to be modified. For more information about ASSL, see [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../../analysis-services/multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).  
  
 If you set the **AllowCreate** attribute of the **Alter** command to true, you can create the specified major object if the object does not exist. Otherwise, an error occurs if a specified major object does not already exist.  
  
### Using the ObjectExpansion Attribute  
 If you are changing only the properties of the major object and are not redefining minor objects that are contained by the major object, you can set the **ObjectExpansion** attribute of the **Alter** command to *ObjectProperties*. The **ObjectDefinition** property then only has to contain the elements for the properties of the major object, and the **Alter** command leaves minor objects associated with the major object untouched.  
  
 To redefine minor objects for a major object, you must set the **ObjectExpansion** attribute to *ExpandFull* and the object definition must include all minor objects that are contained by the major object. If the **ObjectDefinition** property of the **Alter** command does not explicitly include a minor object that is contained by the major object, the minor object that was not included is deleted.  
  
### Altering Session Objects  
 To modify session objects created by the **Create** command, set the **Scope** attribute of the **Alter** command to *Session*.  
  
> [!NOTE]  
>  When using the *Session* setting, the **ObjectDefinition** element can only contain [Dimension](../assl/objects/dimension-element-assl.md), [Cube](../assl/objects/cube-element-assl.md), or [MiningModel](../assl/objects/miningmodel-element-assl.md) ASSL elements.  
  
## Creating or Altering Subordinate Objects  
 Although a **Create** or **Alter** command creates or alters only one topmost major object, the major object being created or modified can contain definitions within the enclosing **ObjectDefinition** property for other major and minor objects that are subordinate to it. For example, if you define a cube, you specify the parent database in **ParentObject**, and within the cube definition in **ObjectDefinition** you can define measure groups for the cube, and within the measure groups you can define partitions for each measure group. A minor object can be defined only under the major object that contains it. For more information about major and minor objects, see [Database Objects &#40;Analysis Services - Multidimensional Data&#41;](../../analysis-services/multidimensional-models/olap-logical/database-objects-analysis-services-multidimensional-data.md).  
  
## Examples  
  
### Description  
 The following example creates a relational data source that references the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] sample [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.  
  
### Code  
  
```  
<Create xmlns="http://schemas.microsoft.com/analysisservices/2003/engine">  
    <ParentObject>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    </ParentObject>  
    <ObjectDefinition>  
        <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
            <ID>AdventureWorksDW2012</ID>  
            <Name>AdventureWorksDW2012</Name>  
            <ConnectionString>Data Source=localhost;Initial Catalog=AdventureWorksDW2008R2;Integrated Security=True</ConnectionString>  
            <ImpersonationInfo>  
                <ImpersonationMode>ImpersonateServiceAccount</ImpersonationMode>  
            </ImpersonationInfo>  
            <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
            <Timeout>PT0S</Timeout>  
        </DataSource>  
    </ObjectDefinition>  
</Create>  
```  
  
### Description  
 The following example alters the relational data source created in the previous example to set the query time-out for the data source to 30 seconds.  
  
### Code  
  
```  
<Alter ObjectExpansion="ObjectProperties" xmlns="http://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <DataSourceID>AdventureWorksDW2012</DataSourceID>  
    </Object>  
    <ObjectDefinition>  
        <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
            <ID>AdventureWorksDW2012</ID>  
            <Name>AdventureWorksDW2012</Name>  
            <ConnectionString>Data Source=fr-dwk-02;Initial Catalog=AdventureWorksDW2008R2;Integrated Security=True</ConnectionString>  
            <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
            <Timeout>PT30S</Timeout>  
        </DataSource>  
    </ObjectDefinition>  
</Alter>  
```  
  
### Comments  
 The **ObjectExpansion** attribute of the **Alter** command was set to *ObjectProperties*. This setting allows the [ImpersonationInfo](../assl/properties/impersonationinfo-element-assl.md) element, a minor object, to be excluded from the data source defined in **ObjectDefinition**. Therefore, the impersonation information for that data source remains set to the service account, as specified in the first example.  
  
## See Also  
 [Execute Method &#40;XMLA&#41;](../xmla/xml-elements-methods-execute.md)   
 [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../../analysis-services/multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)   
 [Developing with XMLA in Analysis Services](../../analysis-services/multidimensional-models-scripting-language-assl-xmla/developing-with-xmla-in-analysis-services.md)  
  

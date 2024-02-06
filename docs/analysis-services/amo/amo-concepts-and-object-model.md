---
title: "AMO Concepts and Object Model | Microsoft Docs"
description: Learn about Analysis Management Objects (AMO) concepts and how AMO is related to other tools and libraries provided in the architecture of Analysis Services.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: amo
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis
monikerRange: "asallproducts-allversions || sql-analysis-services-2016 || sql-analysis-services-2017 || sql-analysis-services-2019 || sql-analysis-services-2022"

---
# AMO concepts and object model

[!INCLUDE[appliesto-sqlas-aas](../includes/appliesto-sqlas-aas.md)]

  This article describes Analysis Management Objects (AMO), how AMO is related to other tools and libraries provided in the architecture of Analysis Services, and a conceptual explanation of all major objects in AMO.  
  
 AMO is a complete collection of management classes that can be used programmatically, under the namespace of <xref:Microsoft.AnalysisServices>, in a managed environment. The classes are included in the AnalysisServices.dll file, which is usually found where setup installs the files, under the folder \100\SDK\Assemblies\\. To use the AMO classes, include a reference to this assembly in your projects.  
  
 By using AMO you can create, modify, and delete objects such as cubes, dimensions, mining structures, and databases; over all these objects, actions can be performed from your application in the .NET Framework. You can also process and update the information stored in databases.  
  
## AMO in the Analysis Services architecture

 By design, AMO is only intended for object management and not for querying data. If the user needs to query data from a client application, the client application should use [ADOMD.NET](../adomd/developing-with-adomd-net.md).  
  
## AMO architecture

 AMO is a complete library of classes designed to manage an Analysis Services instance from a client application in managed code under the .NET Framework version 2.0 and higher.  
  
 The AMO library of classes is designed as a hierarchy of classes, where certain classes must be instantiated before others in order to use them in your code. There are also auxiliary classes that can be instantiated at any time in your code, but you will probably have instantiated one or more of the hierarchy classes before using any one of the auxiliary classes.  
  
 The following illustration is a high-level view of the AMO hierarchy that includes major classes. The illustration shows the placement of the classes among their containers and their peers. A <xref:Microsoft.AnalysisServices.Dimension> belongs to a <xref:Microsoft.AnalysisServices.Database> and a <xref:Microsoft.AnalysisServices.Server>, and can be created at the same time as a <xref:Microsoft.AnalysisServices.DataSource> and <xref:Microsoft.AnalysisServices.MiningStructure>. Certain peer classes must be instantiated before you can use others. For example, you have to create an instance of <xref:Microsoft.AnalysisServices.DataSource> before adding a new <xref:Microsoft.AnalysisServices.Dimension> or <xref:Microsoft.AnalysisServices.MiningStructure>.  
  
 ![AMO Classes High Level View](media/amo-highlevelview-majorobjectshighlighted.png)  
  
 A *major object* is a class that represents a complete object as a whole entity and not as a part of another object. Major objects include <xref:Microsoft.AnalysisServices.Server>, <xref:Microsoft.AnalysisServices.Cube>, <xref:Microsoft.AnalysisServices.Dimension>, and <xref:Microsoft.AnalysisServices.MiningStructure>, because these are entities on their own. However, a <xref:Microsoft.AnalysisServices.Level> is not a major object, because it is a constituent part of a <xref:Microsoft.AnalysisServices.Dimension>. Major objects can be created, deleted, modified, or processed independent of other objects. Minor objects are objects that can only be created as part of creating the parent major object. Minor objects are usually created upon a major object creation. Values for minor objects should be defined at creation time because there is no default creation for minor objects.  
  
 The following illustration shows the major objects that a <xref:Microsoft.AnalysisServices.Server> object contains.  
  
 ![AMO Major Objects highlighted](media/amo-majorobjects.png)  
  
 ![AMO Major Objects highlighted (2)](media/amo-majorobjects-02.png)  
  
 When programming with AMO, the association between classes and contained classes uses collection type attributes, for example <xref:Microsoft.AnalysisServices.Server> and <xref:Microsoft.AnalysisServices.Dimension>. To work with one instance of a contained class, you first acquire a reference to a collection object that holds or can hold the contained class. Next, you find the specific object that you are looking for in the collection, and then you can obtain a reference to the object to start working with it.  
  
### AMO classes

 AMO is a library of classes designed to manage an instance of Analysis Services from a client application. The AMO library can be thought of as logically-related groups of objects that are used to accomplish a specific task. AMO classes can be categorized in the following way:  
  
|Class Set|Purpose|  
|---------------|-------------|  
|[AMO Fundamental Classes](amo-fundamental-classes.md)|Classes required in order to work with any other set of classes.|  
|[AMO OLAP Classes](amo-olap-classes.md)|Classes that let you manage the OLAP objects.|  
|[AMO Data Mining Classes](amo-data-mining-classes.md)|Classes that let you manage the data mining objects.|  
|[AMO Security Classes](amo-security-classes.md)|Classes that let you control access to other objects and maintain security.|  
|[AMO Other Classes and Methods](amo-other-classes-and-methods.md)|Classes and methods that help OLAP or data mining administrators to complete their daily tasks.|  
  
## Using AMO

 AMO is especially useful for automating repetitive tasks, for example creating new partitions in a measure group based on new data in the fact table, or re-training a mining model based on new data. These tasks that create new objects are usually performed on a monthly, weekly, or quarterly basis, and the new objects can easily be named, based in the new data, by the application.  
  
### Analysis Services administrators

 Administrators can use AMO to automate the processing of databases. For designing and deploying databases, use Visual Studio.  
  
### Developers

 Developers can use AMO to develop administrative interfaces for specified sets of users. These interfaces can restrict access to objects and limit users to certain tasks. For example, by using AMO you could create a backup application that enables a user to see all database objects, select any one of the databases, and backup it to any one of a specified set of devices.  
  
 Developers can also embed logic in their applications. For this, developers can create cubes, dimensions, mining structures, and mining models based on user input or other factors.  
  
### OLAP advanced users

 OLAP advanced users are usually data analysts or other experienced data users who have a strong programming background and who want to enhance their data analysis with a closer usage of the data objects. For users who are required to work offline, AMO can be very useful to automate creating local cubes before going offline.  
  
### Data mining advanced users

 For data mining advanced users, AMO is most useful if you have large sets of models that periodically have to be re-trained.  
  
## Automating administrative tasks with AMO

 Most repetitive tasks are best designed, deployed, and maintained if they are developed by using Integration Services than if they are developed as an application in any language of your choice. However, for repetitive tasks that cannot be automated by using Integration Services, you can use AMO.  
  
### Automatic object management

 With AMO it's easy to create, update or delete objects (for example <xref:Microsoft.AnalysisServices.Database>, <xref:Microsoft.AnalysisServices.Dimension>, <xref:Microsoft.AnalysisServices.Cube>, mining <xref:Microsoft.AnalysisServices.MiningStructure>, and <xref:Microsoft.AnalysisServices.MiningModel>, or <xref:Microsoft.AnalysisServices.Role>) based on user input or on new acquired data. AMO is ideal for setup applications that have to deploy a developed solution, from an independent software vendor to a final customer. The setup application can verify that an earlier version exists and can update the structure, remove no longer useful objects, and create new ones. If there is no earlier version then can create everything from scratch.  
  
 AMO can be powerful when creating new partitions based on new data, and can remove old partitions that had gone beyond the scope of the project. For example, for a finance analysis solution that works with the last 36 months of data, as soon as a new month of data is received, the 37th old month could be removed. To optimize performance, new aggregations can be designed based on usage and applied to the last 12 months.  
  
### Automatic object processing

 Object processing and updated availability can be achieved by using AMO to respond to certain events beyond the ordinary flow data and scheduled tasks that use Integration Services.  
  
### Automatic security management

 Security management can be automated to include new users to roles and permissions, or to remove other users as soon as their time has expired. New interfaces can be created to simplify security management for security administrators. This can be simpler than using Visual Studio.  
  
### Automatic backup management

 Automatic backup management can be done by using Integration Services tasks, or by creating specialized AMO applications that run automatically. By using AMO you can develop Backup interfaces for operators that help them in their daily jobs.  
  
### Tasks AMO is not intended for querying data

 AMO cannot be used to query the data. To query data, including cubes and mining models, use ADOMD.NET from a user application. For more information, see [Developing with ADOMD.NET](../adomd/developing-with-adomd-net.md).  

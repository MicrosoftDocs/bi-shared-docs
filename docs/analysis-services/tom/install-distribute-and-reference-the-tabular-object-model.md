---
title: "Install, distribute, and reference the Tabular Object Model | Microsoft Docs"
description: Download, reference, and redistribute Tabular Object Model (TOM), a C# library for creating and managing tabular models and databases in managed code.
ms.date: 12/07/2018
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Install, distribute, and reference the Tabular Object Model

[!INCLUDE[appliesto-sql2016-later-aas-pbip](../includes/appliesto-sql2016-later-aas-pbip.md)]

This article describes how to download, reference, and redistribute Tabular Object Model (TOM), a C# library for creating and managing tabular models and databases in managed code.  
  
TOM is an extension of the AMO client library (Microsoft.AnalysisServices.dll). To use TOM, the model and database must be at compatibility level 1200 or higher.  

## AMO-TOM Assemblies

AMO includes new Core, Tabular, and JSON assemblies. It also includes the original AMO assembly, Microsoft.AnalysisServices.dll, that has been part of Analysis Services since its first release. A restructured AMO offloads common classes to one assembly, and provides a logical division between tabular and multidimensional APIs through additional assemblies. 

The following table describes each assembly:
  
Assembly  |Functionality  |Important classes |
---------|---------|--------------  |
Core <br/>Microsoft.AnalysisServices.Core.dll | Common to both tabular and multidimensional databases. <br/><br/>Provides exception handling, generic connections to a server instance and database, and access to common properties and methods for Server and Database objects. | Core&nbsp;Server<br/>Core&nbsp;Database<br/>AmoException
TOM<br/> Microsoft.AnalysisServices.Tabular.dll, version 13.0.1601.5 or later.| Create and manage tabular metadata objects. | TOM&nbsp;Server <br/>TOM&nbsp;Database<br /> Model<br /> Table<br /> Column<br /> Relationship
  AMO<br /> Microsoft.AnalysisServices.dll| Create and manage multidimensional metadata objects, including tabular 1050-1103 databases. | AMO&nbsp;Server <br />AMO&nbsp;Database <br /> Cube <br /> Dimension <br /> MeasureGroup 
Json<br/>Microsoft.AnalysisServices.Tabular.Json.dll | A helper DLL that wraps the NewtonSoftJson.dll (JSON.NET) to control updates, removing the risk of introducing functional changes to JSON serialization in server workloads. <br /> <br />This DLL exists as a dependency in TOM and is not intended to be used directly in your code. | None.  
  
### Understanding assembly dependencies
  
To program against AMO, your solution must include references to dependent DLLs. Both AMO and TOM depend on Core because it provides base classes.

AMO depends on TOM because some classes in AMO reference classes from TOM. For example, the AMO Database object has a property Model of type Model, implemented in the TOM dll. 

![AMO TOM dependencies](media/amo-tom-dependencies.png)

You can't distribute Microsoft.AnalysisServices.dll without Microsoft.AnalysisServices.Tabular.dll, but you can reference their respective namespaces without the other.

### Choosing which namespace to use in code

In the object hierarchy, any object below Database is either a tabular metadata construction via the Model object, or a multidimensional metadata construction via a Cube, Dimension, or MeasureGroup object. For high-level operations at the Server, Database, Role, or Trace level, the choice of which namespace to reference will depend on the workloads your code needs to support.

* Use Tabular.Server or Tabular.Database if your solution is compatibility level 1200 or higher, and the Database object you work with must provide access to Model, Table, Columns, and other objects expressed as Tabular metadata constructions.
* Use AnalysisServices.Server or AnalysisServices.Database if downstream code references Multidimensional objects such as Cubes, DataSources, DataSourceViews, and Dimensions.

You'll need both namespaces for tools and applications supporting a mix of databases and model types.

Referencing the Core namespace in your code is unnecessary; the classes in Core are base classes created for the purpose of providing common properties, like Name and Description, for major objects.  

## Download and install AMO  
  
1. Go to [Client libraries](../client-libraries.md).  
  
2. Select and download AMO by using Windows Installer or NuGet packages.  

## Add references  
  
1. In **Solution Explorer** > **Add Reference** > **Browse**.  
2. Go to **C:\Program Files\Microsoft SQL Server\140\SDK\Assemblies** and select:  
   * Microsoft.AnalysisServices.Core  
   * Microsoft.AnalysisServices.Tabular  
   * Microsoft.AnalysisSerivces.Tabular.Json  
  
3. Click **OK**.  In **Solution Explorer**, confirm the assemblies exist in the References folder.
  
4. In your code page, add the Microsoft.AnalysisServces.Tabular namespace if databases and models are Tabular 1200 or higher compatibility level.
  
   ```csharp
   using Microsoft.AnalysisServices; 
   using Microsoft.AnalysisServices.Tabular;
   ```  

    When including namespaces that have classes in common for Server, Database, Role, and Trace objects, avoid ambiguous references by qualifying which namespace you want to use (for example, Microsoft.AnalysisServices.Tabular.Server instantiates a Server object using the Tabular namespace).

## Redistribute AMO and TOM with your application  
  
Redistribution of AMO and TOM is through the **sql_as_amo.msi** installation package or NuGet packages. If you are building a setup program for a client application that calls into AMO or TOM, add **sql_as_amo.msi** to your executable. 

The package is self-contained and provides all assemblies required for calling AMO and TOM in your code. Other packages, such as SQL_AS_OLEDB.msi or SQL_AS_ADOMD.msi, are not specifically required for TOM programming scenarios.

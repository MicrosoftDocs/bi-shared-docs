---
title: "ADOMD.NET Client Functionality | Microsoft Docs"
description: Learn how ADOMD.NET not only allows you to retrieve data, but also to retrieve metadata and change the structure of the analytical data store.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: adomd
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# ADOMD.NET Client Functionality
  ADOMD.NET, as with other Microsoft .NET Framework data providers, serves as a bridge between an application and a data source. However, ADOMD.NET is unlike other .NET Framework data providers in that ADOMD.NET works with analytical data. To work with analytical data, ADOMD.NET supports functionality that is very different than other .NET Framework data providers. ADOMD.NET not only allows you to retrieve data, but also to retrieve metadata and change the structure of the analytical data store:  
  
 **Retrieving Metadata**  
 Applications can learn more about the data that can be retrieved from the data source through metadata retrieval, using either schema rowsets or the object model. Information such as the types of each key performance indicator (KPI) that are available, the dimensions in a cube, and the parameters needed by the mining models are all discoverable. Metadata is most important to *dynamic* applications that require user input to determine the type, depth, and scope of data to be retrieved. Examples include Query Analyzer, Microsoft Excel, and other querying tools. Metadata is less critical to *static* applications that perform a predefined set of actions.  
  
 For more information: [Retrieving Metadata from an Analytical Data Source](retrieving-metadata-from-an-analytical-data-source.md).  
  
 **Retrieving Data**  
 Data retrieval is the actual retrieval of the information stored in the data source. Data retrieval is the primary function of "static" applications, which know the structure of the data source. Data retrieval is also the end result of "dynamic" applications. The value of the KPI at a given time of day, the number of bicycles sold within the last hour for each store, and the factors governing the annual performance of employees are all examples of data that can be retrieved. Retrieving data is vital for any querying application.  
  
 For more information: [Retrieving Data from an Analytical Data Source](retrieving-data-from-an-analytical-data-source.md).  
  
 **Changing the Structure of Analytical Data**  
 ADOMD.NET can also be used to actually change the structure of the analytical data store. Though this is usually done through the Analysis Management Objects (AMO) object model, you can use ADOMD.NET to send Analysis Services Scripting Language (ASSL) commands to create, alter, or delete objects on the server.   
  
 Retrieving metadata, retrieving data, and changing data structure each occur at a specific point in the workflow of a typical ADOMD.NET application.  
  
## Typical Process Flow  
 Traditional ADOMD.NET applications usually follow the same workflow when working with an analytical database:  
  
1.  First, a connection is made to the database, using the <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection> object. When you open the connection, the <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection> object exposes metadata about the server to which you have connected. In a dynamic application, some of this information is typically shown to the user so that the user can make a selection, such as which cube to query. The connection created during this step can be reused multiple times by the application, reducing overhead.  
  
     For more information: [Establishing Connections in ADOMD.NET](connections-in-adomd-net.md)  
  
2.  Once a connection has been made, a dynamic application would then query the server for more specific metadata. For a static application, the programmer knows in advance which objects the application will be querying, and thus will not need to retrieve this metadata. Metadata that is retrieved can be used by the application and the user for the next step.  
  
     For more information: [Retrieving Metadata from an Analytical Data Source](retrieving-metadata-from-an-analytical-data-source.md)  
  
3.  The application then runs a command against the server. This command can be for the purpose of retrieving additional metadata, retrieving data, or modifying the database structure. For any of these tasks, the application could use a previously-determined query, or make use of newly retrieved metadata to create additional queries.  
  
     For more information: [Retrieving Metadata from an Analytical Data Source](retrieving-metadata-from-an-analytical-data-source.md), [Retrieving Data from an Analytical Data Source](retrieving-data-from-an-analytical-data-source.md), [Executing Commands Against an Analytical Data Source](executing-commands-against-an-analytical-data-source.md)  
  
4.  Once the command has been sent to the server, the server begins to return the metadata or data to the client. This information can be viewed by using a <xref:Microsoft.AnalysisServices.AdomdClient.CellSet> object, an <xref:Microsoft.AnalysisServices.AdomdClient.AdomdDataReader> object, or a **System.XmlReader** object.  
  
 To illustrate this traditional workflow, the following example contains a method that opens a connection to the database, executes a command against a known cube, and retrieves the results into a cellset. The cellset then returns a tab-delimited string containing column headers, row headers, and cell data.  
  
 [!code-cs[Adomd.NetClient#ReturnCommandUsingCellSet](codesnippet/csharp/adomd-net-client-functio_1.cs)]
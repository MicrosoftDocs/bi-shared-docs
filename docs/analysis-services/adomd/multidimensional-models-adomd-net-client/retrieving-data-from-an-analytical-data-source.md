---
title: "Retrieving Data from an Analytical Data Source | Microsoft Docs"
description: Learn how to retrieve data from an analytical data source by calling one of the Execute methods of the AdomdCommand object.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: adomd
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Retrieving Data from an Analytical Data Source
  Once you make a connection and create the query, you can retrieve any data. In ADOMD.NET, you can retrieve data using three different objects (<xref:Microsoft.AnalysisServices.AdomdClient.CellSet>, <xref:Microsoft.AnalysisServices.AdomdClient.AdomdDataReader>, and <xref:System.Xml.XmlReader>) by calling one of the **Execute** methods of the <xref:Microsoft.AnalysisServices.AdomdClient.AdomdCommand> object.  
  
 Each of these three objects balances interactivity and overhead:  
  
-   *Interactivity* refers to the ease-of-use and amount of information available through the object model.  
  
-   *Overhead* refers to the amount of traffic that an object model generates over the network connection to the server, the amount of memory needed for the object model, and the speed with which the object model retrieves data.  
  
 To help you select the data retrieval object that best suits the needs of your application, the following table highlights the differences between interactivity and overhead for each object.  
  
|Object|Interactivity|Overhead|Retains dimensionality|Usage Information|  
|------------|-------------------|--------------|----------------------------|-----------------------|  
|<xref:Microsoft.AnalysisServices.AdomdClient.CellSet>|Highest|Moderately high, which results in slowest retrieval of data|Yes|[Retrieving Data Using the CellSet](retrieving-data-using-the-cellset.md)|  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdDataAdapter>|Moderate|Moderate|No|[Populating a DataSet from a DataAdapter](/dotnet/framework/data/adonet/populating-a-dataset-from-a-dataadapter)|  
|<xref:Microsoft.AnalysisServices.AdomdClient.AdomdDataReader>|Moderate|Moderate|No|[Retrieving Data Using the AdomdDataReader](retrieving-data-using-the-adomddatareader.md)|  
|<xref:System.Xml.XmlReader>|Lowest|Lowest, which results in fastest data retrieval|Yes|[Retrieving Data Using the XmlReader](retrieving-data-using-the-xmlreader.md)|
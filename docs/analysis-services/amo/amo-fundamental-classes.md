---
title: "AMO Fundamental Classes | Microsoft Docs"
description: Learn how Analysis Management Objects (AMO) fundamental classes help you establish your environment for the rest of the objects that will be used in your application.
ms.date: 07/20/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: amo
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# AMO Fundamental Classes

[!INCLUDE[ssas-appliesto-sqlas-aas](../includes/ssas-appliesto-sqlas-aas.md)]

  Fundamental classes are the starting point for working with Analysis Management Objects (AMO). Through these classes you establish your environment for the rest of the objects that will be used in your application. Fundamental classes include the following objects: <xref:Microsoft.AnalysisServices.Server>, <xref:Microsoft.AnalysisServices.Database>, <xref:Microsoft.AnalysisServices.DataSource>, and <xref:Microsoft.AnalysisServices.DataSourceView>.  
  
 The following illustration shows the relationship of the classes that are explained in this topic.  
  
 ![AMO Fundamental Classes](media/amo-fundamentalclasses.gif)  
  
## Server objects

 Additionally, you will have access to the following methods:  
  
- Connection management: Connect, Disconnect, Reconnect, and GetConnectionState.  
  
- Transaction management: BeginTransaction, CommitTransaction, and RollbackTransaction.  
  
- Backup and Restore.  
  
- DDL execution: Execute, CancelCommand, SendXmlaRequest, StartXmlaRequest.  
  
- Metadata management: UpdateObjects and Validate.  
  
 To connect to a server, you need a standard connection string, as used in ADOMD.NET and OLEDB. For more information, see <xref:System.Configuration.ConnectionStringSettings.ConnectionString>. The name of the server can be specified as a connection string without having to use a connection string format.  
  
 For more information about methods and properties available, see <xref:Microsoft.AnalysisServices.Server> in the <xref:Microsoft.AnalysisServices>.  
  
## Database objects

 To work with a <xref:Microsoft.AnalysisServices.Database> object in your application, you must get an instance of the database from the parent server databases collection. To create a database, you add a <xref:Microsoft.AnalysisServices.Database> object to a server databases collection and update the new instance to the server. To delete a database, you drop the <xref:Microsoft.AnalysisServices.Database> object by using its own Drop method.  
  
 Databases can be backed up by using the BackUp method (from the <xref:Microsoft.AnalysisServices.Database> object or from the <xref:Microsoft.AnalysisServices.Server> object), but can only be restored from the <xref:Microsoft.AnalysisServices.Server> object with the Restore method.  
  
 For more information about methods and properties available, see <xref:Microsoft.AnalysisServices.Database> in the <xref:Microsoft.AnalysisServices>.  
  
## DataSource and DataSourceView Objects

 Data sources are managed by using the <xref:Microsoft.AnalysisServices.DataSourceCollection> from the database class. An instance of <xref:Microsoft.AnalysisServices.DataSource> can be created by using the Add method from a <xref:Microsoft.AnalysisServices.DataSourceCollection> object. An instance of <xref:Microsoft.AnalysisServices.DataSource> can be deleted by using the Remove method from a <xref:Microsoft.AnalysisServices.DataSourceCollection> object.  
  
 <xref:Microsoft.AnalysisServices.DataSourceView> objects are managed from the <xref:Microsoft.AnalysisServices.DataSourceViewCollection> object in the database class.  

 For more information about methods and properties available, see <xref:Microsoft.AnalysisServices.DataSource> and <xref:Microsoft.AnalysisServices.DataSourceView> in the <xref:Microsoft.AnalysisServices>.
---
title: "Test an Analysis Services tabular model in DirectQuery mode | Microsoft Docs"
description: Describes how to test a DirectQuery tabular models by using Analyse in Excel.
ms.date: 08/27/2020
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Test a model in DirectQuery mode

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

Review your options for testing a tabular model in DirectQuery mode at each stage of development, starting with design.  
  
## Test in Excel
  
 When designing your model in SSDT, you can use the **Analyze in Excel** feature to test your modeling decisions against a sample dataset in-memory, or against the relational database.  When you click Analyze in Excel, a dialog box opens where you can specify options.

 ![Analyze in Excel DirectQuery options](../../analysis-services/tabular-models/media/analyze-in-excel-directquery-options.png)

 If your model's DirectQuery mode is on, you can specify DirectQuery connection mode, where you'll have two options:

- **Sample data view** - With this option, any queries from Excel are directed to sample partitions containing a sample dataset in-memory. This option is helpful when you want to make sure any DAX formulas you have in measures, calculated columns, or row-level security perform correctly.
    > [!IMPORTANT]
    > Sample partitions created in Partition Manager are currently not supported. To learn more, see [Adding sample data to a DirectQuery model project](directquery-mode-ssas-tabular.md#adding-sample-data-to-a-directquery-model-project).

- **Full data view** - With this option, any queries from Excel are sent to Analysis Services, and then on to the relational database. This option is, in-effect, fully functioning DirecQuery mode.

### Other clients

 When you use Analyze in Excel, an .odc connection file is created. You can use the connection string information from this file to connect to your model from other client applications. An additional parameter, DataView=Sample, is added to specify the client should connect to sample data partitions.  
  
## Monitor query execution on backend systems using xEvents or SQL Profiler

 Start up a session trace, connected to the SQL Server relational database, to monitor connections coming from the Tabular model:  
  
- [Monitor Analysis Services with SQL Server Extended Events](../../analysis-services/instances/monitor-analysis-services-with-sql-server-extended-events.md)  
  
- [Use SQL Server Profiler to Monitor Analysis Services](../../analysis-services/instances/use-sql-server-profiler-to-monitor-analysis-services.md)  
  
If you're using Oracle or Teradata, use the trace monitoring tools for those systems.  

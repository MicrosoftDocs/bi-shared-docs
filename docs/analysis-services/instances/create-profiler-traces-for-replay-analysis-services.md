---
title: "Create Profiler Traces for Replay (Analysis Services) | Microsoft Docs"
description: Learn how to create profiler traces for replay in SQL Server Analysis Services to replay queries, discovers, and commands.
ms.date: 12/29/2020
ms.service: analysis-services
ms.custom:
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---

# Create Profiler traces for replay (Analysis Services)

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

  To replay queries, discovers, and commands that are submitted by users to Analysis Services, SQL Server Profiler must gather the required events. In order to initiate collection of these events, appropriate event classes must be selected in the **Event Selection** tab of the **Trace Properties** dialog box. For example if the Query Begin event class is selected, events that contain queries are collected and used for replay. Also, the trace file contains sufficient information to support replaying server transactions in a distributed environment in the original sequence of transactions.  
  
## Replay for queries

 To replay queries, SQL Server Profiler must capture the following events:  
  
- Audit Login event class with all its data columns. This event class provides information about which user logged in and about the session settings. The server process ID (SPID) provides the reference to the user session. For more information, see [Security Audit Data Columns](../trace-events/security-audit-data-columns.md).  
  
- Query Begin event class with all its data columns. This event class provides information about the query that was submitted to Analysis Services. The Event Subclass column provides information about the type of query. The TextData column provides the actual text of the query. The RequestParameters column provides the parameters for parameterized queries, and the RequestProperties column provides the properties of an XML for Analysis (XMLA) request. For more information, see [Queries Events Data Columns](../trace-events/queries-events-data-columns.md).  
  
- Query End event class with all its data columns. This event class verifies the status of the query execution. For more information, see [Queries Events Data Columns](../trace-events/queries-events-data-columns.md).  
  
## Replay for Discovers

 To replay discovers, SQL Server Profiler must capture the following events:  
  
- Audit Login event class with all its data columns. This event class provides information about which user logged in and about the session settings. The SPID provides the reference to the user session. For more information, see [Security Audit Data Columns](../trace-events/security-audit-data-columns.md).  
  
- Discover Begin event class with all its data columns. The TextData column provides the \<RequestType> portion of the discover request, and the RequestProperties column provides the \<Properties> portion of the discover request. The EventSubclass column provides the discover type. For more information, see [Discover Events Data Columns](../trace-events/discover-events-data-columns.md).  
  
- Discover End event class with all its data columns. This event class verifies the status of the discover request. For more information, see [Discover Events Data Columns](../trace-events/discover-events-data-columns.md).  
  
## Replay for Commands

 To replay commands, SQL Server Profiler must capture the following events:  
  
- Command Begin event class with all its data columns. The TextData column provides the command details, such as the process type, database ID, and cube ID. The RequestParameters column provides the parameters for parameterized command, and the RequestProperties column provides the properties of an XMLA request. For more information, see [Command Events Data Columns](../trace-events/command-events-data-columns.md).  
  
- Command End event class with all its data columns. This event class verifies the status of the command. For more information, see [Command Events Data Columns](../trace-events/command-events-data-columns.md).  
  
## See also

 [Analysis Services Trace Events](../trace-events/analysis-services-trace-events.md)
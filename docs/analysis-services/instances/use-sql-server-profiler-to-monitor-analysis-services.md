---
title: "Use SQL Server Profiler to Monitor Analysis Services | Microsoft Docs"
description: Learn how to use the SQL Server Profiler to monitor Analysis Services to track engine process events.
ms.date: 12/29/2020
ms.service: analysis-services
ms.custom:
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---

# Monitor Analysis Services with SQL Server Profiler

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

  SQL Server Profiler, installed with SQL Server Management Studio (SSMS), tracks engine process events such as the start of a batch or a transaction. It captures data about those events, enabling you to monitor server and database activity (for example, user queries or login activity). You can capture profiler data to a SQL table or a file for later analysis, and you can also replay the events captured on the same or another Analysis Services instance to see what happened. You can replay events in real time or on a step-by-step basis. It's also useful to run the trace events along with the Performance counters on the same instance. The profiler can correlate these two based on time and display them together along a single timeline. Trace events will give you more details while Performance counters give you an aggregate view. To learn more about how to create and run traces, see [Create Profiler traces for replay &#40;Analysis Services&#41;](../../analysis-services/instances/create-profiler-traces-for-replay-analysis-services.md).  
  
  Use SQL Server Profiler to:  
  
- Monitor the performance of an instance of the Analysis Services engine.  
  
- Debug query statements.  
  
- Identify queries that run slowly.  
  
- Test query statements in the development phase of a project by stepping through statements to confirm that the code works as expected.  
  
- Troubleshoot problems by capturing events on a production system and replaying them on a test system. This approach is useful for testing or debugging purposes and lets users continue to use the production system without interference.  
  
- Audit and review activity that occurred on an instance. A security administrator can review any one of the audited events. This includes the success or failure of a login try and the success or failure of permissions in accessing statements and objects.  
  
- Display data about the captured events to the screen, or capture and save data about each event to a file or SQL table for future analysis or playback. When you replay data, you can rerun the saved events as they originally occurred, either in real time or step by step.  

## Permissions

For Azure Analysis Services and SQL Server Analysis Services, members of the Analysis Services server administrator role can view all server and database traces. Users not in a server administrator role can view traces only for databases in which they are a member of the database administrator role.

For **Power BI Premium**, users can view traces only for databases in which they are a member of the database administrator role. Only those events that require database administrator permissions are available. Trace events requiring server administrator permissions are not available for a Power BI Premium workspace.

## Using SQL Server Profiler

 When using SQL Server Profiler, keep in mind:  
  
- Only database events are available for a **Power BI Premium** workspace. Server events are not available.

- Trace definitions are stored with the Analysis Services database by using the CREATE statement.  
  
- Multiple traces can be running at the same time.  
  
- Multiple connections can receive events from the same trace.  
  
- A trace can continue when Analysis Services stops and restarts.  
  
- Passwords are not revealed in trace events, but are replaced by \*\*\*\*\*\* in the event.  
  
 For optimal performance, use SQL Server Profiler to monitor only those events in which you are most interested. Monitoring too many events adds overhead and can cause the trace file or table to grow very large, especially when you monitor over a long period of time. In addition, use filtering to limit the amount of data that is collected and to prevent traces from becoming too large.

> [!NOTE]
> When connecting to a **Power BI Premium** workspace, a valid database must be specified in the **Connection Properties** tab of the **Connect to Server** dialog, otherwise a  `user does not have permissions to access the object` error message is returned. In the **Connect to Server** dialog, select **Options** > **Connection Properties** > **Connect to database**, enter the dataset name. Additionally, the XMLA read-only setting must be enabled on the Premium capacity.

## See also

 [Analysis Services Trace Events](../trace-events/analysis-services-trace-events.md)  
 [Create Profiler traces for replay Analysis Services](../../analysis-services/instances/create-profiler-traces-for-replay-analysis-services.md)
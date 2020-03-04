---
title: "Use SQL Server Profiler to Monitor Analysis Services | Microsoft Docs"
ms.date: 03/04/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom:
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
#  Monitor Analysis Services with SQL Server Profiler

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

  SQL Server Profiler, installed with SQL Server Management Studio (SSMS) tracks engine process events, such as the start of a batch or a transaction. It captures data about those events, enabling you to monitor server and database activity (for example, user queries or login activity). You can capture profiler data to a SQL table or a file for later analysis, and you can also replay the events captured on the same or another Analysis Services instance to see what happened. You can replay events in real time or on a step-by-step basis. It's also useful to run the trace events along with the Performance counters on the same instance. The profiler can correlate these two based on time and display them together along a single timeline. Trace events will give you more details while Performance counters give you an aggregate view. To learn more about how to create and run traces, see [Create Profiler traces for replay &#40;Analysis Services&#41;](../../analysis-services/instances/create-profiler-traces-for-replay-analysis-services.md).  
  
  Use SQL Server Profiler to:  
  
-   Monitor the performance of an instance of the Analysis Services engine.  
  
-   Debug query statements.  
  
-   Identify queries that run slowly.  
  
-   Test query statements in the development phase of a project by stepping through statements to confirm that the code works as expected.  
  
-   Troubleshoot problems by capturing events on a production system and replaying them on a test system. This approach is useful for testing or debugging purposes and lets users continue to use the production system without interference.  
  
-   Audit and review activity that occurred on an instance. A security administrator can review any one of the audited events. This includes the success or failure of a login try and the success or failure of permissions in accessing statements and objects.  
  
-   Display data about the captured events to the screen, or capture and save data about each event to a file or SQL table for future analysis or playback. When you replay data, you can rerun the saved events as they originally occurred, either in real time or step by step.  
  
## Using SQL Server Profiler

**Permissions** - For Azure Analysis Services and SQL Server Analysis Services, you must be a member of the server admin role. For **Power BI Premium**, only those events that require database admin permissions are available. Those events that require server admin are not available.

 When using SQL Server Profiler, keep in mind:  
  
-   Trace definitions are stored with the Analysis Services database by using the CREATE statement.  
  
-   Multiple traces can be running at the same time.  
  
-   Multiple connections can receive events from the same trace.  
  
-   A trace can continue when Analysis Services stops and restarts.  
  
-   Passwords are not revealed in trace events, but are replaced by \*\*\*\*\*\* in the event.  
  
 For optimal performance, use SQL Server Profiler to monitor only those events in which you are most interested. Monitoring too many events adds overhead and can cause the trace file or table to grow very large, especially when you monitor over a long period of time. In addition, use filtering to limit the amount of data that is collected and to prevent traces from becoming too large.  
  
## See also

 [Analysis Services Trace Events](https://docs.microsoft.com/analysis-services/trace-events/analysis-services-trace-events)   

 [Create Profiler traces for replay &#40;Analysis Services&#41;](../../analysis-services/instances/create-profiler-traces-for-replay-analysis-services.md)  

  
  

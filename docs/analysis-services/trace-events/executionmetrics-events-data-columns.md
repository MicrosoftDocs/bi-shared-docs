---
title: "Execution Metrics Data Columns | Microsoft Docs"
description: Learn about the data columns for the Execution Metrics event category.
ms.date: 02/17/2025
ms.service: analysis-services
ms.custom: trace-events
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Session Events Data Columns

  The Session Events event category has the following event class:  
  
|**Event ID**|**Event Name**|**Event Description**|  
|------------------|--------------------|---------------------------|  
|136|Execution Metrics|Contains execution metrics for the nearest [Discover\|Command\|Query]End event with the same RequestId.|  
  
 The following table lists the data columns for this event class.  
  
## Execution Metrics
  
|**Column Name**|**Column Id**|**Column Type**|**Column Description**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|Event Class is used to categorize events.|  
|ActivityID|46|8|Binary value dependent on the event class captured in the trace.|
|ApplicationName|37|8|Contains the name of the client application that created the connection to the server. This column is populated with the values passed by the application rather than the displayed name of the program.|
|DatabaseName|28|8|Contains the name of the database in which the command was run.|
|Identity|55|8|Identity information of the user.|
|RequestID|47|8|The request ID used to track a request.|
|SPID|41|1|Contains the server process ID (SPID) that uniquely identifies the user session associated with the server state discover event. The SPID directly corresponds to the session GUID used by XMLA.|  
|ServerName|43|8|Contains the name of the instance on which the command event occurred.| 
|TextData|42|9|Contains the execution metrics for the correlated command in JSON format. For details on possible properties, refer to [this document](/power-bi/transform-model/log-analytics/desktop-log-analytics-configure?tabs=refresh#executionmetrics-event).  |
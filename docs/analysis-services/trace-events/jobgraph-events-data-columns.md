---
title: "Job Graph Events Data Columns | Microsoft Docs"
description: Learn about the Job Graph Event class-data columns.
ms.date: 11/11/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: trace-events
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Job Graph Events Data Columns

  The Job Graph Events category has the following event classes:  
  
- Job Graph  
  
 The following tables list the data columns for each of these event classes.  
  
## Job Graph Class—Data Columns

| Column Name | Column Description |
| ----------- | --------- |
|ActivityID|Binary value dependent on the event class captured in the trace.|
|Application Name|Name of the client application that created the connection to the server. This column is populated with the values passed by the application rather than the displayed name of the program.|
|Client Process ID|Contains the process ID of the client application.|
|Connection ID|Contains the unique connection ID associated with the event.|
|CurrentTime|Time at which the event started, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|
|DatabaseName|Name of the database in which the statement of the user is running.|
|EventSubclass|Contains the class of event within the event. Supported values are:<br /><br /> 1: Graph Begin<br /><br /> 2: Graph End|
|Identity|Identity information of current user.|
|IntegerData|An ordinal that identifies the position of a "TextData" portion in the entire graph|
|NTDomainName|Contains the Windows domain associated with the event.|
|NTUserName|Contains the Windows user name associated with the event. The user name is in canonical form. For example, engineering.microsoft.com/software/user.|
|RequestID|The request ID used to track a request.|
|SPID|Contains the server process ID (SPID) that uniquely identifies the user session associated with the event. The SPID directly corresponds to the session GUID used by XMLA.|
|ServerName|Contains the name of the instance on which the event occurred.|
|SessionID|Contains the session ID associated with the event.|
|Success|A binary value that describes event success. 1=success, 0=failure.|
|TextData|A portion of the job graph. The complete job graph can be built only after coalescing the various portions based on their order of occurrence|

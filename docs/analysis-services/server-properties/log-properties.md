---
title: "Analysis Services log properties | Microsoft Docs"
description: Learn how the Analysis Services instance logs server notifications, errors, and warnings to the msmdsrv.log file - one for each instance you install. 
ms.date: 07/21/2022
ms.service: analysis-services
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis
monikerRange: "asallproducts-allversions || azure-analysis-services-current || >= sql-analysis-services-2016"
ms.custom:
  - sfi-ropc-nochange
---
# Log Properties

[!INCLUDE[appliesto-sqlas-all-aas](../includes/appliesto-sqlas-all-aas.md)]

Analysis Services includes log properties listed in the following tables. Not all properties apply to Azure Analysis Services or Power BI. Log properties in Power BI are either Read only or unsupported.

## General

**File**  
A string property that identifies the name of the server log file. This property only applies when a disk file is used for logging, as opposed to a database table (the default behavior).  
  
The default value for this property is msmdsrv.log.  
  
**FileBufferSize**  
An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
**MessageLogs**  
An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
## Error Log

You can set these properties at the server instance level to modify the default values for Error Configuration that appear in other tools and designers. See [Error Configuration for Cube, Partition, and Dimension Processing &#40;SSAS - Multidimensional&#41;](../../analysis-services/multidimensional-models/error-configuration-for-cube-partition-and-dimension-processing.md) and <xref:Microsoft.AnalysisServices.MiningStructure.ErrorConfiguration%2A> for more information.  
  
**ErrorLog\ErrorLogFileName**  
A property used as a default during processing operation performed by the server.  
  
**ErrorLog\ErrorLogFileSize**  
A property used as a default during processing operation performed by the server.  
  
**ErrorLog\KeyErrorAction**  
Specifies the action taken by the server when a **KeyNotFound** error occurs. Valid responses to this error include:  
  
- **ConvertToUnknown** tells the server to allocate the error key value to the unknown member.  
  
- **DiscardRecord** tells the server to exclude the record.  
  
**ErrorLog\KeyErrorLogFile**  
This is a user-defined filename that must have a .log file extension, located in a folder on which the service account has read-write permissions. This log file will only contain errors generated during processing. Use the Flight Recorder if you require more detailed information.  
  
**ErrorLog\KeyErrorLimit**  
This is the maximum number of data integrity errors that the server will allow before failing the processing. A value of -1 indicates that there is no limit. The default is 0, which means processing stops after the first error occurs. You can also set it to a whole number.  
  
**ErrorLog\KeyErrorLimitAction**  
Specifies the action taken by the server when the number of key errors has reached the upper limit. Valid responses to this action include:  
  
- **StopProcessing** tells the server to stop processing when the error limit is reached.  
  
- **StopLogging** tells the server to stop logging errors when the error limit is reached, but allow processing to continue.  
  
**ErrorLog\ LogErrorTypes\KeyNotFound**  
Specifies the action taken by the server when a **KeyNotFound** error occurs. Valid responses to this error include:  
  
- **IgnoreError** tells the server to continue processing without logging the error or counting it towards the key error limit. By ignoring the error, you simply allow processing to continue without adding to the error count or logging it to the screen or log file. The record in question has a data integrity problem and cannot be added to the database. The record will either be discarded or aggregated to Unknown Member, as determined by the **KeyErrorAction** property.  
  
- **ReportAndContinue** tells the server to log the error, count it towards the key error limit, and continue processing. The record triggering the error is discarded or converted to Unknown Member.  
  
- **ReportAndStop** tells the server to log the error and stop processing immediately, regardless of the key error limit. The record triggering the error is discarded or converted to Unknown Member.  
  
**ErrorLog\ LogErrorTypes\KeyDuplicate**  
Specifies the action taken by the server when a duplicate key is found. Valid values include **IgnoreError** to continue processing as if the error did not occur, **ReportAndContinue** to log the error and continue processing, and **ReportAndStop** to log the error and stop processing immediately, even if the error count is below the error limit.  
  
**ErrorLog\ LogErrorTypes\NullKeyConvertedToUnknown**  
Specifies the action taken by the server when a null key has been converted to Unknown Member. Valid values include **IgnoreError** to continue processing as if the error did not occur, **ReportAndContinue** to log the error and continue processing, and **ReportAndStop** to log the error and stop processing immediately, even if the error count is below the error limit.  
  
**ErrorLog\ LogErrorTypes\NullKeyNotAllowed**  
Specifies the action taken by the server when **NullProcessing** is set to **Error** for a dimension attribute. An error is generated when a null value is not allowed in a given attribute. This error configuration property informs the next step, which is to report the error and continue processing until the error limit is reached. Valid values include **IgnoreError** to continue processing as if the error did not occur, **ReportAndContinue** to log the error and continue processing, and **ReportAndStop** to log the error and stop processing immediately, even if the error count is below the error limit.  
  
**ErrorLog\ LogErrorTypes\CalculationError**  
A property used as a default during processing operation performed by the server.  
  
**ErrorLog\IgnoreDataTruncation**  
A property used as a default during processing operation performed by the server.  
  
## Exception
**Exception\CreateAndSendCrashReports**  
An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
**Exception\CrashReportsFolder**  
An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
**Exception\SQLDumperFlagsOn**  
An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
**Exception\SQLDumperFlagsOff**  
An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
**Exception\MiniDumpFlagsOn**  
An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
**Exception\MinidumpErrorList**  
An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
## Flight Recorder
**FlightRecorder\Enabled**  
A Boolean property that indicates whether the flight recorder feature is enabled.  
  
**FlightRecorder\FileSizeMB**  
A signed 32-bit integer property that defines the size of the flight recorder disk file, in megabytes.  
  
**FlightRecorder\LogDurationSec**  
A signed 32-bit integer property that defines the frequency that the flight recorder is rolled over, in seconds.  
  
**FlightRecorder\SnapshotDefinitionFile**  
A string property that defines the name of the snapshot definition file, containing discover commands that are issued to the server when a snapshot is taken.  
  
The default value for this property is blank, which in turn defaults to file name FlightRecorderSnapshotDef.xml.  
  
**FlightRecorder\SnapshotFrequencySec**  
A signed 32-bit integer property that defines the snapshot frequency, in seconds.  
  
**FlightRecorder\TraceDefinitionFile**  
A string property that specifies the name of the flight recorder trace definition file.  
  
The default value for this property is blank, which in turn defaults to FlightRecorderTraceDef.xml. SQL Server Analysis Services Flight Recorder provides a mechanism to record server activity into a short-term log. Information captured by Flight Recorder can be helpful for troubleshooting specific issues, however the load placed on the server when capturing the snapshots and trace events can have a small impact on overall performance.  For optimal performance the flight recorder should be disabled unless attempting to capture diagnostic information relevant to troubleshooting a specific problem. 
  
## Query Log
**Applies to:** Multidimensional server mode only  
  
**QueryLog\QueryLogFileName**  
 A string property that specifies the name of the query log file. This property only applies when a disk file is used for logging, as opposed to a database table (the default behavior).  
  
**QueryLog\QueryLogSampling**  
A signed 32-bit integer property that specifies the query log sampling rate.  
  
The default value for this property is 10, meaning that 1 out of every 10 server queries is logged.  
  
**QueryLog\QueryLogFileSize**  
An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
**QueryLog\QueryLogConnectionString**  
A string property that specifies the connection to the query log database.  
  
**QueryLog\QueryLogTableName**  
A string property that specifies the name of the query log table.  
  
The default value for this property is OlapQueryLog.  
  
**QueryLog\CreateQueryLogTable**  
A Boolean property that specifies whether to create the query log table.  
  
The default value for this property is false, which indicates the server will not automatically create the log table and will not log query events.  
  
## Trace
**Trace\TraceBackgroundDistributionPeriod**  
An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
**Trace\TraceBackgroundFlushPeriod**  
An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
**Trace\TraceFileBufferSize**  
An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
**Trace\TraceFileWriteTrailerPeriod**  
An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
**Trace\TraceMaxRowsetSize**  
An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
**Trace\TraceProtocolTraffic**  
An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
**Trace\TraceQueryResponseTextChunkSize**  
An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
**Trace\TraceReportFQDN**  
An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
**Trace\TraceRequestParameters**  
An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
**Trace\TraceRowsetBackgroundFlushPeriod**  
An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
## See also

[Server properties in Analysis Services](../../analysis-services/server-properties/server-properties-in-analysis-services.md)   
[Determine the Server Mode of an Analysis Services Instance](../../analysis-services/instances/determine-the-server-mode-of-an-analysis-services-instance.md)  

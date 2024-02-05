---
title: "Command Events Data Columns | Microsoft Docs"
description: Learn about the the data columns for each event class in the Command Events event category.
ms.date: 03/04/2022
ms.service: analysis-services
ms.custom: trace-events
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Command Events Data Columns

  The following table lists the data columns for each event class in the **Command Events** event category.  
  
 The **Command Events** event category has the following event classes:  
  
-   [Command Begin class](#bkmk_1)  
  
-   [Command End class](#bkmk_2)  
  
 The following tables list the data columns for each of these event classes.  
  
##  <a name="bkmk_1"></a> Command Begin Class—Data Columns  
  
|Data Column|Description|  
|-----------------|-----------------|  
|ConnectionID|Contains the unique connection ID associated with the command event.|  
|TextData|Contains the text data associated with the command event.|  
|ServerName|Contains the name of the instance on which the command event occurred.|  
|CurrentTime|Contains the current time of the command event.|  
|DatabaseName|Contains the name of the database in which the command is running.|  
|EventSubclass|Contains the class of event within the command event. Supported values are:<br /> 0: Create<br /> 1: Alter<br /> 2: Delete<br /> 3: Process<br /> 4: DesignAggregations<br /> 5: WBInsert<br />6: WBUpdate<br /> 7: WBDelete<br /> 8: Backup<br /> 9: Restore<br /> 10: MergePartitions<br /> 11: Subscribe<br /> 12: Batch<br /> 13: BeginTransaction<br /> 14: CommitTransaction<br /> 15: RollbackTransaction<br /> 16: GetTransactionState<br /> 17: Cancel<br /> 18: Synchronize<br /> 19: Import80MiningModels<br /> 20: Attach<br /> 21: Detach<br /> 22: SetAuthContext<br /> 23: ImageLoad<br /> 24: ImageSave<br /> 25: CloneDatabase<br /> 26: CreateTabular <br /> 27: AlterTabular <br /> 28: DeleteTabular <br /> 29: Refresh <br /> 30: Interpret <br /> 31: ExtAuth<sup>[1](#extauth)</sup> <br /> 32: DBCC (Database Consistency Checks)<br /> 33: RenameTabular <br /> 34: SequencePointTabular <br /> 35: UpgradeTabular <br /> 36: MergePartitionsTabular <br /> 37: DisableDatabase <br /> 38: Tabular JSON Command<br /> 39: Evict <br /> 40: CommitImport <br /> 10000: Other| 
|NTUserName|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service  Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account  (Power BI Service)</br> - Power BI Service on behalf of a UPN or SPN (Power BI Service (UPN/SPN))|
|RequestProperties|Contains the XML for Analysis (XMLA) request properties associated with the command event.|  
|SPID|Contains the server process ID (SPID) that uniquely identifies the user session that is associated with the command event. The SPID directly corresponds to the session GUID used by XMLA.|  
|StartTime|Contains the time at which the command event started, if available.|  
|SessionType|Contains the entity that caused the operation.|  
|NTDomainName|Contains the domain name associated with the user account that triggered the command event. </br> - Windows domain name for Windows user accounts</br> - AzureAD for Microsoft Entra accounts</br> - NT AUTHORITY accounts without a Windows domain name, such as the Power BI service|
|ClientProcessID|Contains the unique client process ID associated with the command event.|  
  
##  <a name="bkmk_2"></a> Command End Class—Data Columns  
  
|Data Column|Description|  
|-----------------|-----------------|  
|ConnectionID|Contains the unique connection ID associated with the command event.|  
|TextData|Contains the text data associated with the command event.|  
|ServerName|Contains the name of the instance on which the command event occurred.|  
|CurrentTime|Contains the current time of the command event. For filtering, the formats are *YYYY*-*MM*-*DD* and *YYYY*-*MM*-*DD HH*:*MM*:*SS*.|  
|DatabaseName|Contains the name of the database in which the command is running.|  
|Duration|Contains the approximate amount of time between the command begin and the command end event.|  
|EndTime|Contains the time at which the command event ended. For filtering, the formats are *YYYY*-*MM*-*DD* and *YYYY*-*MM*-*DD HH*:*MM*:*SS*.|  
|EventSubclass|Contains the class of event within the command event. Supported values are:<br /> 0: Create<br /> 1: Alter<br /> 2: Delete<br /> 3: Process<br /> 4: DesignAggregations<br /> 5: WBInsert<br />6: WBUpdate<br /> 7: WBDelete<br /> 8: Backup<br /> 9: Restore<br /> 10: MergePartitions<br /> 11: Subscribe<br /> 12: Batch<br /> 13: BeginTransaction<br /> 14: CommitTransaction<br /> 15: RollbackTransaction<br /> 16: GetTransactionState<br /> 17: Cancel<br /> 18: Synchronize<br /> 19: Import80MiningModels<br /> 20: Attach<br /> 21: Detach<br /> 22: SetAuthContext<br /> 23: ImageLoad<br /> 24: ImageSave<br /> 25: CloneDatabase<br /> 26: CreateTabular <br /> 27: AlterTabular <br /> 28: DeleteTabular <br /> 29: Refresh <br /> 30: Interpret <br /> 31: ExtAuth<sup>[1](#extauth)</sup><br /> 32: DBCC (Database Consistency Checks)<br /> 33: RenameTabular <br /> 34: SequencePointTabular <br /> 35: UpgradeTabular <br /> 36: MergePartitionsTabular <br /> 37: DisableDatabase <br /> 38: Tabular JSON Command<br /> 39: Evict <br /> 40: CommitImport <br /> 10000: Other|
|NTCanonicalUserName|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account (Power BI Service)|
|NTUserName|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service  Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account  (Power BI Service)</br> - Power BI Service on behalf of a UPN or SPN (Power BI Service (UPN/SPN))|
|SPID|Contains the server process ID (SPID) that uniquely identifies the user session associated with the command event. The SPID directly corresponds to the session GUID used by XMLA.|  
|StartTime|Contains the time at which the command end event started, if available.|  
|CPUTime|Contains the amount of CPU time (in milliseconds) used by the process between the time of the command begin event and the command end event.|  
|Error|Contains the error number of any error associated with the command event.|  
|Severity|Contains the severity level of an exception associated with the command event. Values are:<br /><br /> 0 = Success<br /><br /> 1 = Informational<br /><br /> 2 = Warning<br /><br /> 3 = Error|  
|Success|Contains the success or failure of the command event. Values are:<br /><br /> 0 = Failure<br /><br /> 1 = Success|  
|SessionType|Contains the entity that caused the operation associated with the command end event.|  
|NTDomainName|Contains the domain name associated with the user account that triggered the command event. </br> - Windows domain name for Windows user accounts</br> - AzureAD for Microsoft Entra accounts</br> - NT AUTHORITY accounts without a Windows domain name, such as the Power BI service|
|ClientProcessID|Contains the unique client process ID associated with the command event.|  

<a name="extauth">1</a> - An internal service-generated command to perform authentication.

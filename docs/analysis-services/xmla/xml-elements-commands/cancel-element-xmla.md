---
title: "Cancel Element (XMLA) | Microsoft Docs"
description: Learn how the Cancel element cancels a currently running command an Analysis Services instance. 
ms.date: 07/24/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Cancel Element (XMLA)

  Cancels a currently running command an Analysis Services instance.  
  
## Syntax  
  
```xml  
  
<Command>  
   <Cancel>  
      <ConnectionID>...</ConnectionID>  
      <SessionID>...</SessionID>  
      <SPID>...</SPID>  
      <CancelAssociated>...</CancelAssociated>  
   </Cancel>  
</Command>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Command](../xml-elements-properties/command-element-xmla.md)|  
|Child elements|[CancelAssociated](../xml-elements-properties/cancelassociated-element-xmla.md), [ConnectionID](../xml-elements-properties/connectionid-element-xmla.md), [SessionID](../xml-elements-properties/sessionid-element-xmla.md), [SPID](../xml-elements-properties/spid-element-xmla.md)|  
  
## Remarks  
 The **Cancel** command cancels currently executing commands within the context of a session. If the client application has not requested a session, a command cannot be canceled.  
  
 If the **Cancel** command is executed during the execution of a **Batch** command, the entire **Batch** command is canceled. If the **Batch** command was transactional, all of the commands contained by the **Batch** command are rolled back. If the **Batch** command was not transactional, only those commands contained by the **Batch** command that were executing at the time the **Cancel** command was executed are rolled back. Commands in a non-transactional **Batch** command that had already executed would not be rolled back.  
  
 Typically, the **Cancel** command is used to cancel executing commands on the currently active session. In that case, none of the child elements for the **Cancel** command must be specified. The **Cancel** command can also be used by administrators to cancel commands executing on connections or sessions other than the currently active session. Members of a role that has Administer permissions for a given database can cancel commands for connections and sessions applicable to that database, while server administrators can cancel commands for connections and sessions for a given Analysis Services instance.  
  
 To retrieve information about current connections and sessions for an Analysis Services instance, the **Discover** method can be executed to request, respectively, the DISCOVER_CONNECTIONS and DISCOVER_SESSIONS schema rowsets. Members of a role that has Administer permissions for a given database can return sessions only for a given database by specifying that database in the SESSION_CURRENT_DATABASE restriction column for the DISCOVER_SESSIONS schema rowset. For more information about the **Discover** method, see [Discover Method &#40;XMLA&#41;](../xml-elements-methods-discover.md).  
 
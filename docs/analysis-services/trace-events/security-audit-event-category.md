---
title: "Security Audit Event Category | Microsoft Docs"
description: Learn about the event classes for the Security Audit event category.
ms.date: 05/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: trace-events
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Security Audit Event Category

  The Security Audit event category has the event classes described in the following table.  
  
|Event Class|Event Id|Description|  
|-----------------|--------------|-----------------|  
|Audit Login|1|Records all new connection events since the trace started, such as when a client requested a connection to a server running an instance of Analysis Services.|  
|Audit Logout|2|Records all new disconnect events since the trace started, such as when a client issues a disconnect command.|  
|Audit Server Starts and Stops|4|Records shutdown, start, and pause activities for services.|  
|Audit Object Permission Event|18|Records all object permission changes.|  
|Audit Admin Operations Event|19|Records server operations for backup, restore, synchronize, attach, detach, image load, and image save.|  
  
 For information about the columns associated with each of the Security Audit event classes, see [Security Audit Data Columns](security-audit-data-columns.md).  
  


---
title: "RollbackTransaction Element (XMLA) | Microsoft Docs"
description: Learn how the RollbackTransaction element rolls back a transaction on the current session with an instance of Analysis Services.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# RollbackTransaction Element (XMLA)

  Rolls back a transaction on the current session with an instance of Analysis Services.  
  
## Syntax  
  
```xml  
  
<Command>  
   <RollbackTransaction />  
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
|Child elements|None|  
  
## Remarks  
 The **RollbackTransaction** command rolls back all active transactions, explicitly defined using the **BeginTransaction** element, on the current session. If an active transaction does not already exist, an error occurs. If an active transaction already exists, the Analysis Services instance decrements the reference count of transactions for the current session to zero, rolling back all active transactions.
---
title: "CommitTransaction Element (XMLA) | Microsoft Docs"
description: Learn how the CommitTransaction element commits a transaction on the current session with a Analysis Services instance.
ms.date: 01/05/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# CommitTransaction Element (XMLA)

  Commits a transaction on the current session with a Analysis Services instance.  
  
## Syntax  
  
```xml  
  
<Command>  
   <CommitTransaction />  
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
 The **CommitTransaction** command commits an active transaction, explicitly defined using the **BeginTransaction** element, on the current session. If an active transaction does not already exist, an error occurs. If an active transaction already exists, the Analysis Services instance decrements the reference count of transactions for the current session. If the reference count of explicitly defined active transactions reaches zero, the Analysis Services instance commits the transaction.  

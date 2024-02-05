---
title: "Lock Element (XMLA) | Microsoft Docs"
description: Learn how the Lock element locks a specified object on a Analysis Services instance.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Lock Element (XMLA)

  Locks a specified object on a Analysis Services instance.  
  
## Syntax  
  
```xml  
  
<Command>  
   <Lock>  
      <ID>...</ID>  
      <Object>...</Object>  
      <Mode>...</Mode>  
   </Lock>  
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
|Child elements|[ID](../xml-elements-properties/id-element-xmla.md), [Mode](../xml-elements-properties/mode-element-xmla.md), [Object](../xml-elements-properties/object-element-xmla.md)|  
  
## Remarks  
 The **Lock** command locks an object, either for shared or exclusive use, within the context of the currently active transaction. Only database administrators or server administrators can explicitly issue a **Lock** command. A lock on an object prevents transactions from committing until the lock is removed. Analysis Services supports two types of locks, shared locks and exclusive locks. 
  
 Analysis Services allows only databases to be locked. The **Object** element must contain an object reference to an Analysis Services database. If the **Object** element is not specified or if the **Object** element refers to an object other than a database, an error occurs.  
  
 Other commands implicitly issue a **Lock** command on an Analysis Services database. Any operation that reads data or metadata from a database, such as any **Discover** method or an **Execute** method running a **Statement** command, implicitly issues a shared lock on the database. Any transaction that commits changes in data or metadata to an object on an Analysis Services database, such as an **Execute** method running an **Alter** command, implicitly issues an exclusive lock on the database.  
  
 All locks are held in the context of the current transaction. When the current transaction is committed or rolled back, all locks defined within the transaction are automatically released.  
 
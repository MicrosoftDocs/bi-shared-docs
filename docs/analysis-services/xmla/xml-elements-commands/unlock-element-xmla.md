---
title: "Unlock Element (XMLA) | Microsoft Docs"
ms.date: 07/24/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfilee"
---
# Unlock Element (XMLA)

  Unlocks a specified lock on a Analysis Services instance.  
  
## Syntax  
  
```xml  
  
<Command>  
   <Unlock>  
      <ID>...</ID>  
   </Unlock>  
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
|Child elements|[ID](../xml-elements-properties/id-element-xmla.md)|  
  
## Remarks  
 The **Unlock** command removes a lock established within the context of the currently active transaction. Only database administrators or server administrators can explicitly issue an **Unlock** command.  
  
 All locks are held in the context of the current transaction. When the current transaction is committed or rolled back, all locks defined within the transaction are automatically released.  

---
title: "results Element (XMLA) | Microsoft Docs"
description: Learn how the results element contains a collection of root elements returned by the Execute method using the Batch command. 
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# results Element (XMLA)

  Contains a collection of [root](../xml-elements-properties/root-element-xmla.md) elements returned by the [Execute](../xml-elements-methods-execute.md) method using the [Batch](../xml-elements-commands/batch-element-xmla.md) command.  
  
 **Namespace** `http://schemas.microsoft.com/analysisservices/2003/xmla-multipleresults`  
  
## Syntax  
  
```xml  
  
<return>  
   <results>  
      <root>...</root>  
   </results>  
</return>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[return](../xml-elements-properties/return-element-xmla.md)|  
|Child elements|[root](../xml-elements-properties/root-element-xmla.md)|  
  
## Remarks  
 If a **Batch** command is executed by the **Execute** method, the **return** element contains a single **results** element instead of a single **root** element. The content of the **results** element depends on the settings used to run the **Batch** command.  
  
 For non-transactional **Batch** commands, the **results** element contains one **root** element for each command executed by the **Batch** command, whether the command completes successfully or unsuccessfully. For transactional **Batch** commands, the **results** element contains only one **root** element, which contains the error information for the command that failed within the **Batch** command.  

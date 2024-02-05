---
title: "ReadWriteMode Element | Microsoft Docs"
description: Learn how the ReadWriteMode element specifies whether the database is in ReadWrite mode or in ReadOnly mode. 
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# ReadWriteMode Element

  The **ReadWriteMode** database property specifies whether the database is in **ReadWrite** mode or in **ReadOnly** mode. These are the only two possible values of the property.  
  
## Syntax  
  
```xml  
  
<Database>  
...  
   <ddlns_100_0:ReadWriteMode>...</ddlns_100_0:ReadWriteMode>  
...  
</Database>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|ReadWrite|  
|Cardinality|0-1: Optional element that can occur more than once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Database](../xml-elements-properties/database-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 Databases are created in **ReadWrite** mode only. Databases cannot be created in **ReadOnly** mode.  
  
 The value of the **ReadWriteMode** element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*ReadOnly*|No changes or updates can be applied to the database.|  
|*ReadWrite*|Changes and updates can be applied to the database.|  

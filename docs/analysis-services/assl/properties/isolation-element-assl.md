---
title: "Isolation Element (ASSL) | Microsoft Docs"
description: Learn about the Isolation property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# Isolation Element (ASSL)

  Indicates the isolation level for an element that is derived from the [DataSource](../data-type/datasource-data-type-assl.md) data type.  
  
## Syntax  
  
```xml  
  
<DataSource>  
   ...  
   <Isolation>...</Isolation>  
   ...  
</DataSource>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*ReadCommitted*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[DataSource](../data-type/datasource-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value for this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*ReadCommitted*|Specifies that statements cannot read data that has been modified but not committed by other transactions. This prevents dirty reads. Other transactions can change data between individual statements within the current transaction. This results in nonrepeatable reads or phantom data. This value is the default for the **Isolation** element.|  
|*Snapshot*|Specifies that the data that is read by any statement in a transaction will be the transactionally consistent version of the data that existed at the start of the transaction. The transaction can only see data modifications that were committed before the start of the transaction. Data modifications that are made by other transactions after the start of the current transaction are not visible to statements that are executing in the current transaction. The effect is as if the statements in a transaction get a snapshot of the committed data as it existed at the start of the transaction.|  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

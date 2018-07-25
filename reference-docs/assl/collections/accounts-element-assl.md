---
title: "Accounts Element (ASSL) | Microsoft Docs"
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Accounts Element (ASSL)

  Contains the collection of account types that are defined in a [Database](objects/database-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Database>  
   ...  
   <Accounts>  
      <Account>...</Account>  
   </Accounts>  
   ...  
</Database>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None (collection)|  
|Default value|None (collection)|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Database](objects/database-element-assl.md)|  
|Child elements|[Account](objects/account-element-assl.md)|  
  
## Remarks  
 Dimensions, whose [Type](properties/type-element-dimension-assl.md) element is set to *Accounts*, can have an attribute that specifies the account type, such as Income, Expense, and so on, represented by members in the dimension. The account type is then used by [Measure](objects/measure-element-assl.md) elements, whose [AggregationFunction](properties/aggregatefunction-element-assl.md) element is set to *ByAccount*, to determine the aggregation function to use when aggregating the members of that dimension. The **Accounts** element holds a collection of **Account** elements, which represent account types and the aggregation function that should be used for each account type.  
  
 An account type must be listed if the aggregate function is different from the default used by Analysis Services for each account type.  
  
 The set of valid account types is fixed.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.AccountCollection>.  

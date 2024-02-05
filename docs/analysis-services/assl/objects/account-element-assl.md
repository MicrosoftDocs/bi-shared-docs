---
title: "Account Element (ASSL) | Microsoft Docs"
description: Learn about the Account object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Account Element (ASSL)

  Contains details about an account type within a [Database](database-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Accounts>  
   <Account>  
      <AccountType>...</AccountType>  
      <AggregationFunction>...</AggregationFunction>  
            <Aliases>...</Aliases>  
            <Annotations>...</Annotations>  
   </Account>  
</Accounts>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Accounts](../collections/accounts-element-assl.md)|  
|Child elements|[AccountType](../properties/accounttype-element-assl.md), [AggregationFunction](../properties/aggregationfunction-element-assl.md), [Aliases](../collections/aliases-element-assl.md), [Annotations](../collections/annotations-element-assl.md)|  
  
## Remarks  
 Dimensions, whose [Type](../properties/type-element-dimension-assl.md) element is set to *Accounts,* can have an attribute that specifies the account type, such as Income, Expense, and so on, represented by members in the dimension. The account type is then used by [Measure](../objects/measure-element-assl.md) elements, whose [AggregationFunction](../properties/aggregatefunction-element-assl.md) element is set to *ByAccount*, to determine the aggregation function to use when aggregating the members of that dimension. The **Account** element represents a single account type and the aggregation function that should be used by such measures.  
  
 An account type must be listed if the aggregate function is different from the default used by Analysis Services for each account type.  
  
 The set of valid account types is fixed.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Account>.  
  
## See Also  
 [Database Element &#40;ASSL&#41;](../objects/database-element-assl.md)   
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  

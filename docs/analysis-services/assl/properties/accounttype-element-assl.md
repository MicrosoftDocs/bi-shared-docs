---
title: "AccountType Element (ASSL) | Microsoft Docs"
description: Learn about the AccountType property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# AccountType Element (ASSL)

  Contains the name of an account type defined in a [Database](../objects/database-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Account>  
   ...  
   <AccountType>...</AccountType>  
   ...  
</Account>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Account](../objects/account-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Income*|The account is an income account.|  
|*Expense*|The account is an expense account.|  
|*Flow*|The account is a cash flow account.|  
|*Balance*|The account is a balance account.|  
|*Asset*|The account is an asset account.|  
|*Liability*|The account is a liability account.|  
|*Statistical*|The account is a statistical account.|  
  
 The enumeration corresponding to the allowed values for **AccountType** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.AccountTypes>.  
  
## See Also  
 [Accounts Element &#40;ASSL&#41;](../collections/accounts-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

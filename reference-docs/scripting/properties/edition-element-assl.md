---
title: "Edition Element (ASSL) | Microsoft Docs"
ms.date: 5/8/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
---
# Edition Element (ASSL)

  Contains the read-only edition of the instance of Microsoft SQL Server represented by the [Server](../../../analysis-services/scripting/objects/server-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Server>  
      ...  
      <Edition>...</Edition>  
   ...  
</Server>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Server](../../../analysis-services/scripting/objects/server-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The **Edition** element describes which edition of Analysis Services is installed. The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Standard*|Microsoft SQL Server Standard edition for 32-bit processors.|  
|*Enterprise*|Microsoft SQL Server Enterprise edition for 32-bit processors.|  
|*EnterpriseCore*|Microsoft SQL Server Enterprise edition: Core-based Licensing for 32-bit processors.|  
|*BusinessIntelligence*|Microsoft SQL Server Business Intelligence edition for 32-bit processors.|  
|*Developer*|Microsoft SQL Server Developer edition for 32-bit processors|  
|*Evaluation*|Microsoft SQL Server Evaluation edition for 64-bit processors.|  
|*Local*|Microsoft SQL Server Local edition for 32-bit processors.|  
|*Standard64*|Microsoft SQL Server Standard edition for 64-bit processors.|  
|*Enterprise64*|Microsoft SQL Server Enterprise edition for 64-bit processors.|  
|*EnterpriseCore64*|Microsoft SQL Server Enterprise edition: Core-based Licensing for 64-bit processors.|  
|*BusinessIntelligence64*|Microsoft SQL Server Business Intelligence edition for 64-bit processors.|  
|*Developer64*|Microsoft SQL Server Developer edition for 64-bit processors|  
|*Evaluation64*|Microsoft SQL Server Evaluation edition for 64-bit processors.|  
|*Local64*|Microsoft SQL Server Local edition for 64-bit processors.|  
  
 The enumeration corresponding to the allowed values for **ServerEdition** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ServerEdition>.  
  
## See Also  
 [Version Element &#40;ASSL&#41;](../../../analysis-services/scripting/properties/version-element-assl.md)   
 [Properties &#40;ASSL&#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  

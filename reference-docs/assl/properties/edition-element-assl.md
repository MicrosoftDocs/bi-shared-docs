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

  Contains the read-only edition of the instance of  represented by the [Server](../../../analysis-services/scripting/objects/server-element-assl.md) element.  
  
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
 The **Edition** element describes which edition ofAnalysis Services is installed. The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Standard*| Standard edition for 32-bit processors.|  
|*Enterprise*| Enterprise edition for 32-bit processors.|  
|*EnterpriseCore*| Enterprise edition: Core-based Licensing for 32-bit processors.|  
|*BusinessIntelligence*| Business Intelligence edition for 32-bit processors.|  
|*Developer*| Developer edition for 32-bit processors|  
|*Evaluation*| Evaluation edition for 64-bit processors.|  
|*Local*| Local edition for 32-bit processors.|  
|*Standard64*| Standard edition for 64-bit processors.|  
|*Enterprise64*| Enterprise edition for 64-bit processors.|  
|*EnterpriseCore64*| Enterprise edition: Core-based Licensing for 64-bit processors.|  
|*BusinessIntelligence64*| Business Intelligence edition for 64-bit processors.|  
|*Developer64*| Developer edition for 64-bit processors|  
|*Evaluation64*| Evaluation edition for 64-bit processors.|  
|*Local64*| Local edition for 64-bit processors.|  
  
 The enumeration corresponding to the allowed values for **ServerEdition** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ServerEdition>.  
  
## See Also  
 [Version Element &#40;ASSL&#41;](../../../analysis-services/scripting/properties/version-element-assl.md)   
 [Properties &#40;ASSL&#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  

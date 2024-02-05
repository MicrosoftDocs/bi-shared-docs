---
title: "UnknownMember Element (ASSL) | Microsoft Docs"
description: Learn about the UnknownMember property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# UnknownMember Element (ASSL)

  Indicates whether the unknown member is visible.  
  
## Syntax  
  
```xml  
  
<Dimension>  
      ...  
   <UnknownMember>...</UnknownMember>  
   ...  
</Dimension>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*None*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[Dimension](../objects/dimension-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Visible*|The unknown member exists and is displayed.|  
|*Hidden*|The unknown member exists but is not displayed.|  
|*None*|The unknown member is not used.|  
  
 The enumeration that corresponds to the allowed values for **UnknownMember** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.UnknownMemberBehavior>.  
  
## See Also  
 [UnknownMemberName Element &#40;ASSL&#41;](unknownmembername-element-assl.md)   
 [UnknownMemberTranslation Element &#40;ASSL&#41;](../objects/unknownmembertranslation-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

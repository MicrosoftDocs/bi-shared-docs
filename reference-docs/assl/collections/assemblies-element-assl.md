---
title: "Assemblies Element (ASSL) | Microsoft Docs"
ms.date: 07/25/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Assemblies Element (ASSL)

  Contains the collection of [Assembly](objects/assembly-element-assl.md) elements associated with a [Server](objects/server-element-assl.md) or [Database](objects/database-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Server> <!-- or Database -->  
   ...  
   <Assemblies>  
      <Assembly xsi:type="ClrAssembly">...</Assembly>  
            <Assembly xsi:type="ComAssembly">...</Assembly>  
   </Assemblies>  
   ...  
</Server>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Database](objects/database-element-assl.md), [Server](objects/server-element-assl.md)|  
|Child elements|[Assembly](objects/assembly-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.AssemblyCollection>.  

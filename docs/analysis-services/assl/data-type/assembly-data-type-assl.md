---
title: "Assembly Data Type (ASSL) | Microsoft Docs"
description: Learn about the Assembly data type element in the Analysis Services Scripting Language (ASSL) schema.
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
# Assembly Data Type (ASSL)

  Defines an abstract primitive data type that represents a Microsoft .NET Framework assembly or a COM dynamic link library (DLL) associated with a [Server](../objects/server-element-assl.md) or [Database](../objects/database-element-assl.md) element.  
  
> [!IMPORTANT]  
>  COM assemblies might pose a security risk. Due to this risk and other considerations, COM assemblies are depreceated.
  
## Syntax  
  
```xml  
  
<Assembly>  
   <Name>...</Name>  
   <ID>...</ID>  
   <Description>...</Description>  
   <CreatedTimestamp>...</CreatedTimestamp>  
   <LastSchemaUpdate>...</LastSchemaUpdate>  
   <ImpersonationInfo>...</ImpersonationInfo>  
   <Annotations>...</Annotations>  
</Assembly>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|None|  
|Derived data types|ClrAssembly, ComAssembly|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[Annotations](../collections/annotations-element-assl.md), [CreatedTimestamp](../properties/createdtimestamp-element-assl.md), [Description](../properties/description-element-assl.md), [ID](../properties/id-element-assl.md), [ImpersonationInfo](../properties/impersonationinfo-element-assl.md), [LastSchemaUpdate](../properties/lastschemaupdate-element-assl.md), [Name](../properties/name-element-assl.md)|  
|Derived elements|None|  
  
## Remarks  
 The **Assembly** data type serves as the base data type for the **ComAssembly** element, which represents COM libraries associated with the instance or database, and the **ClrAssembly** element, which represents assemblies associated with the instance or database.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Assembly>.  

  
  

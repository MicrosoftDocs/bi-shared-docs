---
title: "PermissionSet Element (ASSL) | Microsoft Docs"
description: Learn about the PermissionSet property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# PermissionSet Element (ASSL)

  Identifies the permission set associated with a  .NET Framework assembly.  
  
## Syntax  
  
```xml  
  
<ClrAssembly>  
   ...  
   <PermissionSet>...</PermissionSet>  
  
</ClrAssembly>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Safe*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[ClrAssembly](../data-type/clrassembly-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Safe*|Only internal computation and local data access is allowed. *Safe* is the most restrictive permission set. Code executed by an assembly with *Safe* permissions cannot access external system resources such as files, the network, environment variables, or the registry.|  
|*ExternalAccess*|*Safe*, with the additional ability to access external system resources such as files, networks, environmental variables, and the registry.|  
|*Unrestricted*|Unrestricted allows assemblies unrestricted access to resources, both within and outside . Code executing from within an *Unrestricted* assembly can call unmanaged code.|  
  
 The enumeration that corresponds to the allowed values for **PermissionSet** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.PermissionSet>.  
  
## See Also  
 [ComAssembly Data Type &#40;ASSL&#41;](../data-type/comassembly-data-type-assl.md)   
 [Assemblies Element &#40;ASSL&#41;](../collections/assemblies-element-assl.md)   
 [Database Element &#40;ASSL&#41;](../objects/database-element-assl.md)   
 [Server Element &#40;ASSL&#41;](../objects/server-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  

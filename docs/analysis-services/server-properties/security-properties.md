---
title: "Analysis Services security properties | Microsoft Docs"
description: Learn about the available security properties in Analysis Services, like RequireClientAuthentication and ServiceAccountIsServerAdmin.
ms.date: 07/21/2022
ms.service: analysis-services
ms.custom: 
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || >= sql-analysis-services-2016"
---
# Security properties

[!INCLUDE[appliesto-sqlas-all-aas](../includes/appliesto-sqlas-all-aas.md)]

Analysis Services supports the following security properties.

## Properties

**AdministrativeDataProtection\ RequiredProtectionLevel**  An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  

**BuiltinAdminsAreServerAdmins**  
Does not apply to Power BI. A Boolean property that indicates whether members of the local machine administrators group are administrators.

**DataProtection\ RequiredProtectionLevel**  
A signed 32-bit integer property that defines the required protection level for all client requests. This property has one of the values listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*0*|None, clear text allowed.|  
|*1*|(Default) Encryption required, no clear-text logging.|  
|*2*|Clear-text requests allowed but only with signatures (weaker protection than encryption).|

**DisableClientImpersonation**  
A Boolean property that indicates whether client impersonation (for example, from stored procedures) is disabled.  
  
The default value for this property is False, which indicates that client impersonation is enabled.

**ErrorMessageMode**  
An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  

**RequireClientAuthentication**  
A Boolean property that indicates whether client authentication is required.  
  
The default value for this property is True, which indicates that client authentication is required.  
  
**SecurityPackageList**  
Does not apply to Power BI. A string property that contains a comma-separated list of SSPI packages used by the server for client authentication.  
  
**ServiceAccountIsServerAdmin**  
Does not apply to Power BI. A Boolean property that indicates whether the service account is a server administrator.  
  
The default value for this property is True, which indicates that the service account is a server administrator.  
  
## See also

 [Server properties in Analysis Services](../../analysis-services/server-properties/server-properties-in-analysis-services.md)   
 [Determine the Server Mode of an Analysis Services Instance](../../analysis-services/instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  

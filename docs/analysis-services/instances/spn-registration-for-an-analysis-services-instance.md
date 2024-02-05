---
title: "SPN registration for an Analysis Services instance | Microsoft Docs"
description: Learn how to register a Service Principal Name for a SQL Server Analysis Services instance for use with authentication.
ms.date: 05/02/2018
ms.service: analysis-services
ms.custom:
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan
monikerRange: "asallproducts-allversions || >= sql-analysis-services-2016"
---
# SPN registration for an Analysis Services instance
[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]
  A Service Principal Name (SPN) uniquely identifies a service instance in an Active Directory domain when Kerberos is used to mutually authenticate client and service identities. An SPN is associated with the logon account under which the service instance runs.  
  
 For client applications connecting to Analysis Services via Kerberos authentication, the Analysis Services client libraries construct an SPN using the host name from the connection string and other well-known variables, such as the service class, that are fixed in any given release of Analysis Services.  
  
 For mutual authentication to occur, the SPNs constructed by the client must match a corresponding SPN object on an Active Directory Domain Controller (DC). This means that you might need to register multiple SPNs for a single Analysis Services instance to cover all of the ways in which a user might specify the host name on a connection string. For example, you probably need two SPNs to handle both the fully-qualified domain name (FQDN) of a server, as well as the short computer name. Correctly registering the Analysis Services SPN is essential for a successful connection. If the SPN is non-existent, malformed, or duplicated, the connection will fail.  
  
 SPN registration is a manual task performed by the Analysis Services administrator. Unlike the SQL Server database engine, Analysis Services never auto-registers its SPN at service startup. Manual registration is required when Analysis Services runs under the default virtual account, a domain user account, or a built-in account, including a per-service SID.  
  
 SPN registration is not required if the service runs under a predefined managed service account created by a domain administrator. Note that depending on the functional level of your domain, registering an SPN can require domain administrator permissions.  
  
> [!TIP]  
>  **[!INCLUDE[msCoName](../includes/msconame-md.md)] Kerberos Configuration Manager for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]** is a diagnostic tool that helps troubleshoot Kerberos related connectivity issues with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. For more information, see [Microsoft Kerberos Configuration Manager for SQL Server](https://www.microsoft.com/download/details.aspx?id=39046).  
  
 This topic contains the following sections:  
  
 [When SPN registration is required](#bkmk_scnearios)  
  
 [SPN format for Analysis Services](#bkmk_SPNSyntax)  
  
 [SPN registration for a virtual account](#bkmk_virtual)  
  
 [SPN registration for a domain account](#bkmk_domain)  
  
 [SPN registration for a built-in account](#bkmk_builtin)  
  
 [SPN registration for a named instance](#bkmk_spnNamed)  
  
 [SPN registration for an SSAS cluster](#bkmk_spnCluster)  
  
 [SPN registration for SSAS instances configured for HTTP access](#bkmk_spnHTTP)  
  
 [SPN registration for SSAS instances listening on fixed ports](#bkmk_spnFixedPorts)  
  
##  <a name="bkmk_scnearios"></a> When SPN registration is required  
 Any client connection that specifies "SSPI=Kerberos" on the connection string will introduce SPN registration requirements for an Analysis Services instance.  
  
 SPN registration is required under the following circumstances. For more detailed information, see [Configure Analysis Services for Kerberos constrained delegation](../../analysis-services/instances/configure-analysis-services-for-kerberos-constrained-delegation.md).  
  
-   Identity delegation is necessary to flow the user identity from the client application or middle-tier service to Analysis Services. Identity delegation is typically used when per-user permissions or filters are defined on specific objects.  
  
     A common scenario involving identity delegation is configuring middle-tier services, such as Excel Services or Reporting Services, for constrained delegation for the purpose of impersonating a user identity when retrieving data in Analysis Services. To support this behavior, you must provide an Analysis Services SPN as the destination service when configuring Excel Services or Reporting Services for constrained delegation.  
  
-   Analysis Services delegates a user identity when retrieving data from a SQL Server relational database for tabular databases using DirectQuery mode. This is the only scenario in which Analysis Services will delegate the user identity to another service.  
  
##  <a name="bkmk_SPNSyntax"></a> SPN format for Analysis Services

 Use **setspn** to register an SPN. On newer operating systems, **setspn** is installed as a system utility. For more information, see [SetSPN](https://technet.microsoft.com/library/cc731241\(WS.10\).aspx).  
  
 The following table describes each part of an Analysis Services SPN.  
  
|Element|Description|  
|-------------|-----------------|  
|Service class|MSOLAPSvc.3 identifies the service as an Analysis Services instance. The .3 is a reference to the version of the XMLA-over-TCP/IP protocol used in Analysis Services transmissions. It's unrelated to product release. As such, MSOLAPSvc.3 is the correct service class for SQL Server 2005, 2008, 2008 R2, 2012, and any future release of Analysis Services until the protocol itself is revised.|  
|Host-name|Identifies the computer on which the service is running. This can be a fully-qualified domain name or a NetBIOS name. You should register an SPN for both.<br /><br /> When registering an SPN for the NetBIOS name of a server, be sure to use `SetupSPN -S` to check for duplicate registration. NetBIOS names aren't guaranteed to be unique in a forest, and having a duplicate SPN registration will cause the connection to fail.<br /><br /> For Analysis Services load balanced clusters, the host name should be the virtual name assigned to the cluster.<br /><br /> Never create an SPN using the IP address. Kerberos uses the DNS resolution capabilities of the domain. Specifying an IP address bypasses that capability.|  
|Port-number|Although the port number is part of SPN syntax, you never specify a port number when registering an Analysis Services SPN. The colon ( : ) character, typically used to provide a port number in standard SPN syntax, is used by Analysis Services to specify the instance name. For an Analysis Services instance, the port is assumed to be the default port (TCP 2383) or a port assigned by the SQL Server Browser service (TCP 2382).|  
|Instance-name|Analysis Services is a replicable service that can be installed multiple times on the same computer. Each instance is identified through its instance name.<br /><br /> The instance name is prefixed with a colon ( : ) character. For example, given a host computer named SRV01 and a named instance of SSAS-Tabular, the SPN should be SRV01:SSAS-Tabular.<br /><br /> Note that the syntax for specifying a named Analysis Services instance differs from that used by other SQL Server instances. Other services uses a backslash ( \ ) to append the instance name in an SPN.|  
|Service-account|This is the startup account of the **MSSQLServerOLAPService** Windows service. It can be a Windows domain user account, virtual account, managed service account (MSA) or a built-in account such as a per-service SID, NetworkService, or LocalSystem. A Windows domain user account can be formatted as domain\user or user@domain.|  
  
##  <a name="bkmk_virtual"></a> SPN registration for a virtual account

 Virtual accounts are the default account type for SQL Server services. The virtual account is **NT Service\MSOLAPService** for a default instance and **NT Service\MSOLAP$**\<instance-name> for a named instance.  
  
 As the name implies, these accounts do not exist in Active Directory. A virtual account exists only on the local computer. When connecting to external services, applications, or devices, the connection is made using the local machine account. For this reason, an SPN registration for Analysis Services running under a virtual account is actually an SPN registration for the machine account.  
  
 **Example syntax for a default instance running as NT Service\MSOLAPService**  
  
 This example shows **setspn** syntax for Analysis Services default instance running under the default virtual account. In this example, the computer host name is **AW-SRV01**. As noted, SPN registration must specify the *machine account* instead of the virtual account, **NT Service\MSOLAPService**.  
  
```  
Setspn -s MSOLAPSvc.3/AW-SRV01.AdventureWorks.com AW-SRV01  
```  
  
> [!NOTE]  
>  Remember to create two SPN registrations, one for the NetBIOS host name and a second for a fully-qualified domain name of the host. Different client applications use different host name conventions when connecting to Analysis Services. Having two SPN registrations ensures that both versions of the host name are accounted for.  
  
 **Example syntax for a named instance running as NT Service\MSOLAP$\<instance-name>**  
  
 This example shows **setspn** syntax for a named instance running under the default virtual account. In this example, the computer host name is **AW-SRV02**, and the instance name is **AW-FINANCE**. Again, it is the machine account that is specified for the SPN, rather than the virtual account **NT Service\MSOLAP$**\<instance-name>.  
  
```  
Setspn -s MSOLAPSvc.3/AW-SRV02.AdventureWorks.com:AW-FINANCE AW-SRV02  
```  
  
##  <a name="bkmk_domain"></a> SPN registration for a domain account

 Using a domain account to run an Analysis Services instance is a common practice.  
  
 For Analysis Services instances that run in a network or hardware load balanced cluster, a domain account is required, with each instance in the cluster running under the same domain account.  
  
**Example syntax for a default instance running as a domain user**
  
 This example shows **setspn** syntax for Analysis Services default instance running under a domain user account, **SSAS-Service**, in the AdventureWorks domain.  
  
```  
Setspn -s msolapsvc.3/AW-SRV01.Adventureworks.com AdventureWorks\SSAS-Service  
```  
  
> [!TIP]  
>  Verify whether the SPN was created for the Analysis Services server by running `Setspn -L <domain account>` or `Setspn -L <machinename>`, depending on how the SPN was registered. You should see MSOLAPSVC.3/\<hostname> in the list.  
  
##  <a name="bkmk_builtin"></a> SPN registration for a built-in account  
 Although this practice is not recommended, older Analysis Services installations are sometimes configured to run under built-in accounts like Network Service, Local Service, or Local System.  
  
 **Example syntax for a default instance running under a built-in account**  
  
 SPN registration for a service running under a built-in account or per-service SID is equivalent to the SPN syntax used for the virtual account. Instead of the account name, use the machine account:  
  
```
Setspn -s MSOLAPSvc.3/AW-SRV01.AdventureWorks.com AW-SRV01  
```

##  <a name="bkmk_spnNamed"></a> SPN registration for a named instance

By default, named instances of Analysis Services use dynamic port assignments that are detected by the SQL Server Browser service. You only need to create a NetBIOS and FQDN SPNs for the named instance to enable Kerberos connections.

### Example syntax for a named instance running as a domain user

The following example shows the `setspn` syntax for Analysis Services named instance `AW-FINANCE` running under a domain user account, SSAS-Service, in the AdventureWorks domain. In this example, the computer host name is AW-SRV01.

```  
FQDN SPN: Setspn -s MSOLAPSvc.3/AW-SRV01.AdventureWorks.com:AW-FINANCE AdventureWorks\SSAS-Service 

NetBIOS SPN: Setspn -s MSOLAPSvc.3/AW-SRV01:AW-FINANCE AdventureWorks\SSAS-Service 
```

> [!NOTE]
> If you configured your named instance to listen on a fixed port, perform the following steps to use Kerberos connections from your client application:
> 1. Start the SQL Server Browser service.
> 1. If you're using a port number in your connection string, remove the port number, add the instance name, and let the application receive the port number through the SQL Server Browser service.

> [!TIP]
> Verify whether the SPN was created for the SQL named instance by running the `Setspn -L <domain account>` or `Setspn -L <machinename>` command, depending on how the SPN was registered.

Microsoft Kerberos Configuration Manager for SQL Server is a diagnostic tool that helps troubleshoot Kerberos related connectivity issues with SQL Server. This tool can help identify potential problems in SPNs and delegations and provide automated procedures to fix the identified issues. For more information, see [Microsoft Kerberos Configuration Manager for SQL Server](https://www.microsoft.com/download/details.aspx?id=39046).  

##  <a name="bkmk_spnCluster"></a> SPN registration for an SSAS cluster  

For Analysis Services failover clusters, the host name should be the virtual name assigned to the cluster. This is the SQL Server network name, specified during SQL Server Setup when you installed Analysis Services on top of an existing WSFC. You can find this name in Active Directory. You can also find it in **Failover Cluster Manager** | **Role** | **Resources** tab. The server name on the Resources tab is what should be used as the 'virtual name' in the SPN command.  
  
**SPN syntax for an Analysis Services cluster**

```
Setspn -s msolapsvc.3/<virtualname.FQDN > <domain user account>  
```  
  
 Recall that nodes in an Analysis Services cluster are required to use the default port (TCP 2383) and run under the same domain user account so that each node has the same SID. See [How to Cluster SQL Server Analysis Services](/previous-versions/sql/sql-server-2012/dn736073(v=msdn.10)) for more information.  
  
##  <a name="bkmk_spnHTTP"></a> SPN registration for SSAS instances configured for HTTP access
 Depending on solution requirements, you might have configured Analysis Services for HTTP access. If your solution includes IIS as a middle tier component, and Kerberos authentication is a solution requirement, you might need to manually register an SPN for IIS. For more information, see "Configure the settings on the computer running IIS" in [How to configure SQL Server 2008 Analysis Services and SQL Server 2005 Analysis Services to use Kerberos authentication](https://support.microsoft.com/kb/917409).  
  
 In terms of SPN registration for the Analysis Services instance, there is no difference between an instance configured for TCP or HTTP. The connection to Analysis Services from IIS, using the MSMDPUMP ISAPI extension, is always TCP.  
  
 This means that you can use the instructions from previous sections for default or named instance to register the SPN. When specifying the host name, be sure to use the host name you specified in the msmdpump.ini file when you configured the service for HTTP access.  
  
 For more information about HTTP access, see [Configure HTTP Access to Analysis Services on Internet Information Services &#40;IIS&#41; 8.0](../../analysis-services/instances/configure-http-access-to-analysis-services-on-iis-8-0.md).  
  
##  <a name="bkmk_spnFixedPorts"></a> SPN registration for SSAS instances listening on fixed ports

You can't specify a port number on an Analysis Services SPN registration.The Analysis Services SPN registration can only use instance name. If you installed Analysis Services as a default instance and configured it to listen on a non-default port, you can't connect to that instance using Kerberos. You must configure it to listen on the default port (TCP 2383) for enabling Kerberos connections to that instance. A default instance of Analysis Services listening on non-default port can only accept NTLM connections. For named instances, you need to start SQL Server Browser service and use instance names in your connection strings instead of port numbers.
  
 An Analysis Services instance can only listen on a single port. Using multiple ports isn't supported. For more information about port configuration, see [Configure the Windows Firewall to Allow Analysis Services Access](../../analysis-services/instances/configure-the-windows-firewall-to-allow-analysis-services-access.md).  
  
## See Also

 [Microsoft BI Authentication and Identity Delegation](/previous-versions/sql/sql-server-2012/dn186184(v=msdn.10))   
 [Mutual Authentication Using Kerberos](/windows/win32/ad/mutual-authentication-using-kerberos)    
 [Service Principal Names (SPNs) SetSPN Syntax (Setspn.exe)](https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx)   
 [SetSPN](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/cc731241(v=ws.11))   
 [Service Accounts Step-by-Step Guide](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd548356(v=ws.10))   
 [Configure Windows Service Accounts and Permissions](/sql/database-engine/configure-windows/configure-windows-service-accounts-and-permissions)   
 [How to use SPNs when you configure Web applications that are hosted on Internet Information Services](https://support.microsoft.com/kb/929650)   
 [what's new in service accounts](https://technet.microsoft.com/library/dd367859\(WS.10\).aspx)   
 [Configure Kerberos authentication for SharePoint 2010 Products (white paper)](/previous-versions/office/sharepoint-server-2010/ff829837(v=office.14))  

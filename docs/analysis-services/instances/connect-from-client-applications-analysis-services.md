---
title: "Connect to SQL Server Analysis Services | Microsoft Docs"
description: Learn how to connect to an instance of SQL Server Analysis Services with common tools and how to connect under different user identities for testing purposes.
ms.date: 04/22/2020
ms.service: analysis-services
ms.custom:
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan
monikerRange: "asallproducts-allversions || >= sql-analysis-services-2016"
---
# Connect to SQL Server Analysis Services

[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]

This article describes connecting to an instance of SQL Server Analysis Services (SSAS) using common tools and applications. This article also explains how to connect under different user identities for testing purposes.  

To learn about connecting to **Azure Analysis Services**, see [Connecting to server resources](/azure/analysis-services/analysis-services-connect)

To learn about connecting to **Power BI Premium workspaces**, see [Connecting to a Premium workspace](/power-bi/service-premium-connect-tools#connecting-to-a-premium-workspace)
  
## Firewall and permissions

Successful connections to SSAS depend on a valid port configuration and appropriate user permissions. Click the following links to learn more about each requirement.  

- [Configure the Windows Firewall to Allow Analysis Services Access](../../analysis-services/instances/configure-the-windows-firewall-to-allow-analysis-services-access.md)  
  
- [Authorizing access to objects and operations &#40;Analysis Services&#41;](../../analysis-services/multidimensional-models/authorizing-access-to-objects-and-operations-analysis-services.md)  

> [!NOTE]
> The client libraries required by client applications cannot connect to Analysis Services through proxy servers that require a username and password.
  
## Connect using SQL Server Management Studio (SSMS)

Connect to Analysis Services in SSMS to manage server instances and databases interactively. You can also run XMLA or MDX queries to perform administrative tasks or retrieve data. In contrast with other tools and applications that only load databases when a query is sent, SSMS loads all databases when you connect to the server, assuming you have permission to view the database. This means that if you have numerous tabular databases on the server, all are loaded into system memory when you connect using SSMS.  
  
You can test permissions by running SSMS under a specific user identity and then connect to Analysis Services as that user.  
  
Hold-down the Shift key and right-click the **SQL Server Management Studio** shortcut to access the **Run as different user** option.  
  
1.  Start [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]. In the **Connect to Server** dialog box, select the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server type.  
  
2.  In the Login tab, enter the server name by typing the name of the computer on which the server is running. You can specify the server using its network name or a fully-qualified domain name.  
  
     For a named instance, the server name must be specified in this format: servername\instance name. An example of this naming convention might be ADV-SRV062\Finance for a server that has a network name of ADV-SRV062, where Analysis Services was installed as a named instance entitled Finance.  
  
     For servers deployed in a failover cluster, connect using the network name of the SSAS cluster. This name is specified during SQL Server setup, as **SQL Server Network Name**. Note that if you installed SSAS as a named instance onto a Windows Server Failover Cluster (WSFC), you never add the instance name on the connection. This practice is unique to SSAS; in contrast, a named instance of a clustered relational database engine does include the instance name. For example, if you installed both SSAS and the database engine as named instance (Contoso-Accounting) with a SQL Server Network Name of SQL-CLU, you would connect to SSAS using "SQL-CLU" and to the database engine as "SQL-CLU\Contoso-Accounting". See [How to Cluster SQL Server Analysis Services](/previous-versions/sql/sql-server-2012/dn736073(v=msdn.10)) for more information and examples.  
  
     For servers deployed in a network load balanced cluster, connect using the virtual server name of the NLB.  
  
3.  Authentication is always Windows authentication, and the user identity is always the Windows user who is connecting via Management Studio.  
  
     In order for the connection to succeed, you must have permission to access the server or a database on the server. Most tasks that you want to perform in Management Studio require administrative permissions. Ensure that the account you are connecting with is a member of the Server Administrator role. For more information, see [Grant server admin rights to an  Analysis Services instance](../../analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance.md).  
  
4.  Click **Connection Properties** to specify a particular database, set timeout values, or encryption options. Optional connection information includes connection properties used for the current connection only.  
  
5.  Click **Additional Connection Parameters** tab to set connection properties not available in the Connect to Server dialog box. For example, you might type `Roles=Reader` in the text box.  
  
     Connecting through a role with less permission lets you test database behaviors when that role is in effect.  
  
    ```  
    Provider=MSOLAP; Data Source=SERVERNAME; Initial Catalog=AdventureWorks2012; Roles=READER  
    ```  
  
## Connect using Excel

Microsoft Excel is often used for analyzing business data. As part of an Excel installation, Office installs the Analysis Services OLE DB provider (MSOLAP DLL), ADOMD.NET, and other data providers so that you can more readily use the data on your network servers. If you are using a newer version of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] with an older version of Excel, you most likely need to install newer client libraries on each workstation that connects to [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]. To learn more, see [Client libraries](../client-libraries.md).  
  
When you set up a connection to an Analysis Services cube or tabular model database, Excel saves the connection information in .odc file for future use. The connection is made in security context of the current Windows user. The user account must have read permissions on the database in order for the connection to succeed.  
  
When using [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data in an Excel workbook, connections are held for the duration of a query request. This is why you are likely to see lots of connections for each session, held for very short periods of time, when monitoring a query workload from Excel.  
  
You can test permissions by starting Excel under a specific user identity.  
  
Hold-down the Shift key and right-click the **Excel** shortcut to access the **Run as different user** option.  
  
1.  On the Data tab in Excel, click **From Other Sources**, and then click **From Analysis Services**. Enter the server name, and then select a cube or perspective to query.  
  
     For servers deployed in a load-balanced cluster, use the virtual server name assigned to the cluster.  
  
2.  When setting up a connection in Excel, on the last page of the Data Connection Wizard, you can specify authentication settings for Excel Services. These settings are used to set properties on the workbook should you upload it to a SharePoint server that has Excel Services. The settings are used in data refresh operations. Options include **Windows Authentication**, **Secure Store Service** (SSS), and **None**.  
  
     Avoid using **None**. Analysis Services does not let you specify a user name and password on the connection string unless you are connecting to a server that has been configured for HTTP access. Similarly, do not use SSS unless you already know that the SSS target application ID is mapped to a set of Windows user credentials that have user access to the Analysis Services databases. For most scenarios, using the default option of Windows authentication is the best choice for an Analysis Services connection from Excel.  
  
 For more information, see [Connect to or import data from SQL Server Analysis Services](https://go.microsoft.com/fwlink/?linkID=215150).  
  
## Connect using Visual Studio

 Visual Studio with Analysis Services projects is used for building BI solutions. When building reports or packages, you might need to specify a connection to Analysis Services.  
  
 The following links explain how to connect to Analysis Services from a Report Server project or an Integration Services project:  
  
- [Analysis Services Connection Type for MDX &#40;SSRS&#41;](/sql/reporting-services/report-data/analysis-services-connection-type-for-mdx-ssrs)  
  
- [Analysis Services Connection Manager](/sql/integration-services/connection-manager/analysis-services-connection-manager)  
  
> [!NOTE]  
>  When using Visual Studio to work on an existing Analysis Services project, remember that you can connect offline using a local or version controlled project, or connect in online mode to update Analysis Services objects while the database is running. For more information, see [Connect in Online Mode to an Analysis Services Database](../../analysis-services/multidimensional-models/connect-in-online-mode-to-an-analysis-services-database.md). More commonly, connections from [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] are in project mode, where changes are deployed to the database only when you explicitly deploy the project.  
  
## Test connections

Use SQL Server Profiler to monitor connections to Analysis Services. The Audit Login and Audit Logout events provide evidence of a connection. The identity column indicates the security context under which the connection is made.  
  
1.  Start **SQL Server Profiler** on the Analysis Services instance and then start a new trace.  
  
2.  In Events Selection, verify that **Audit Login** and **Audit Logout** are checked in the Security Audit section.  
  
3.  Connect to Analysis Services via an application service (such as SharePoint or Reporting Services) from a remote client computer. The Audit Login event will show the identity of the user connecting to Analysis Services.  
  
 Connection errors are often traced to an incomplete or invalid server configuration. Always check server configuration first:  
  
-   Ping the server from a remote computer to ensure it allows remote connections.  
  
-   **Firewall rules on the server allow inbound connections from clients in the same domain**  
  
     With the exception of [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] for SharePoint, all connections to a remote server require that you have configured the firewall to allow access to the port that Analysis Services is listening on. If you are getting connection errors, verify that the port is accessible and that user permissions are granted to the appropriate databases.  
  
     To test, use Excel or SSMS to on a remote computer, specifying the IP address and port used by the Analysis Services instance. If you can connection, the firewall rules are valid for the instance and the instance allows remote connections.  
  
     Also, when using TCP/IP for the connection protocol, remember that Analysis Services requires client connections originate from the same domain or a trusted domain. If connections flow across security boundaries, you will most likely need to configure HTTP access. For more information, see [Configure HTTP Access to Analysis Services on Internet Information Services &#40;IIS&#41; 8.0](../../analysis-services/instances/configure-http-access-to-analysis-services-on-iis-8-0.md).  
  
-   Can you connect using some tools but not others? The problem might be the wrong version of a client library. You can get client libraries from the SQL Server Feature Pack download page.  
  
 Resources that can help you resolve connection failures include the following:  
  
 [Resolving Common Connectivity Issues in SQL Server 2005 Analysis Services Connectivity Scenarios](/previous-versions/sql/sql-server-2005/administrator/cc917670(v=technet.10)). This document is a few years old, but the information and methodologies still apply.  
  
## See Also  

 [Authentication methodologies supported by Analysis Services](../../analysis-services/instances/authentication-methodologies-supported-by-analysis-services.md)   
 [Impersonation](../../analysis-services/tabular-models/impersonation-ssas-tabular.md)   
 [Create a Data Source &#40;SSAS Multidimensional&#41;](../../analysis-services/multidimensional-models/create-a-data-source-ssas-multidimensional.md)  
  

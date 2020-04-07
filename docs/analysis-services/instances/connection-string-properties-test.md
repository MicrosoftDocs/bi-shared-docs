---
title: "Connection string properties (Analysis Services) | Microsoft Docs"
ms.date: 04/07/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom:
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Connection string properties (TEST MONIKERS)

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

This article describes connection string properties used by client applications that connect to and query Azure Analysis Services (Azure AS), SQL Server Analysis Services (SSAS), and Power BI Premium dataset data.

Use the **Version** selector above the table of contents to the left to see only those properties that apply to a particular platform or version.

Properties described here are used by the Analysis Services client libraries, ADOMD.NET, AMO, and OLE DB (MSOLAP) provider for Analysis Services. The majority of connection string properties can be used with all three client libraries. Exceptions are called out in the description.

## Connection properties

The following properties apply to Azure Analysis Services, Power BI Premium, and SQL Server Analysis Services.

### Data Source

Specifies the server instance. This property is required for all connections.

::: moniker range="asallproducts-allversions || azure-analysis-services-current"

Valid values for Azure Analysis Services include `<protocol>://<region>/<servername>` where protocol is string `asazure` or `link` when using a [server name alias](https://docs.microsoft.com/azure/analysis-services/analysis-services-server-alias), region is the Uri where the server was created (for example, westus.asazure.windows.net), and servername is the name of your unique server within the region.

::: moniker-end

::: moniker range="asallproducts-allversions || power-bi-premium-current"

Valid values for Power BI Premium include `<protocol>://api.powerbi.com/v1.0/[tenant name]/[workspace name]` where protocol is string `powerbi`, Uri is api.powerbi.com, tenant name is the organization tenant name or myorg, and workspace name is the name of a workspace assigned to a dedicated capacity.

::: moniker-end

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

Valid values for SQL Server Analysis Services include the network name or IP address of the server, local or localhost for local connections, a URL if the server is configured for HTTP or HTTPS access, or the name of a local cube (.cub) file.

::: moniker-end

#### Examples

::: moniker range="asallproducts-allversions || azure-analysis-services-current"

`Data source=asazure://westus.asazure.windows.net/myasserver` for Azure Analysis Services.

`Data source=link://friendlyname.salesapp.azurewebsites.net/` for Azure Analysis Services using server name alias.

::: moniker-end

::: moniker range="asallproducts-allversions || power-bi-premium-current"

`Data source=powerbi://api.powerbi.com/v1.0/contoso.com/Sales Workspace` for Power BI Premium workspace.

::: moniker-end

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

`Data source=AW-SRV01` for an SSAS default instance and port (TCP 2383).

`Data source=AW-SRV01\Finance` for an SSAS named instance.

`Data source=AW-SRV01:8081` for an SSAS default instance and specified port.

`Data source=AW-SRV01.corp.Adventure-Works.com` for an SSAS fully qualified domain name, assuming the default instance and port.

`Data source=172.16.254.1` for an SSAS IP address of the server, bypassing DNS server lookup, useful for troubleshooting connection problems.

::: moniker-end

### Initial Catalog or Catalog

Specifies the name of the Analysis Services database or Power BI Premium dataset to connect to. The database must be deployed on Analysis Services or a Power BI Premium workspace, and you must have permission to connect to it. By default for SSAS, the first allowed database is automatically selected. For Azure AS and Power BI Premium, a database is not automatically selected, but a catalog can be specified using the Catalog property after opening the connection. This property is optional for AMO connections but required for ADOMD.NET.

#### Example

`Initial catalog=AdventureWorks`

### Provider

This property is required on the connection string when using an OLE DB provider like MSOLAP. It allows you to use either a version independent provider (usually the latest) like `"Provider=MSOLAP"`, or you can also specify a version dependent provider like `"Provider=MSOLAP.7"`. Valid version dependent values follow the pattern `MSOLAP.<version>`, where `<version>` is either `7` or `8`. For example, MSOLAP.7 released in SQL Server 2016. Version ".8" is the latest and considered "evergreen". It's expected to keep updating with backward compatibility maintained. Earlier version numbers are also possible, but those releases of MSOLAP are now out of standard support.

This property is optional for ADOMD.NET and AMO. It's allowed for convenience when copying an MSOLAP connection string to use with ADOMD.NET and AMO.

#### Example

`Provider=MSOLAP.7` used for connections that require the SQL Server 2016 version of the OLE DB provider for Analysis Services.

### Cube

Cube name or perspective name. A database can contain multiple cubes and perspectives. When multiple targets are possible, include the cube or perspective name on the connection string.

#### Example

`Cube=Sales` to specify a cube named Sales.

`Cube=SalesPerspective` to specify a perspective named SalesPerspective.

## Authentication and security properties

Azure Analysis Services and Power BI Premium use Azure Active Directory - Universal with MFA (recommended), Azure Active Directory authentication with username and password, or Windows authentication.

SQL Server Analysis Services uses Windows authentication only, but you can set properties on the connection string to pass in a specific user name and password.  
  
Properties are listed in alphabetical order.

::: moniker range="asallproducts-allversions || azure-analysis-services-current || >= sql-analysis-services-2016"

### EffectiveUserName

Use when an end user identity must be impersonated on the server. For SSAS, specify in a domain\user format. For Azure AS, specify in UPN format. To use this property, the caller must have administrative permissions in Analysis Services. For more information about using this property in an Excel workbook from SharePoint, see [Use Analysis Services EffectiveUserName in SharePoint Server 2013](https://go.microsoft.com/fwlink/?LinkId=311905).

::: moniker-end

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

### Encrypt Password

Specifies whether a local password is to be used to encrypt local cubes. Valid values are True or False. The default is False.

::: moniker-end

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

### Encryption Password

The password used to decrypt an encrypted local cube. Default value is empty. This value must be explicitly set by the user.

::: moniker-end

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

### Impersonation Level

Indicates the level of impersonation that the server is allowed to use when impersonating the client. Valid values include:

- **Anonymous**. The client is anonymous to the server. The server process cannot obtain information about the client, nor can the client be impersonated. 
- **Identify**. The server process can get the client identity. The server can impersonate the client identity for authorization purposes but cannot access system objects as the client.
- **Impersonate**. This is the default value. The client identity can be impersonated, but only when the connection is established, and not on every call. 
- **Delegate**. The server process can impersonate the client security context while acting on behalf of the client. The server process can also make outgoing calls to other servers while acting on behalf of the client.

::: moniker-end

### Integrated Security

The Windows identity of the caller is used to connect to Analysis Services. Valid values are blank, SSPI, BASIC, and ClaimsToken*.

`Integrated Security=SSPI` is the default value for TCP connections, allowing NTLM, Kerberos, or Anonymous authentication. Blank is the default value for HTTP connections.

For Azure AS and Power BI Premium **SSPI** indicates AD Translation.

*`Integrated Security=ClaimsToken` is supported for Azure AS and Power BI Premium.

When using SSPI, **ProtectionLevel** must be set to one of the following: Connect, PktIntegrity, PktPrivacy.

### Persist Security Info

Valid values are True and False. When set to True, security information, such as the user identity or password previously specified on the connection string, can be obtained from the connection after the connection is made. The default value is False.

### Protection Level

Determines the security level used on the connection. Valid values are:

- **None**. Unauthenticated or anonymous connections. Performs no authentication on data sent to the server.
- **Connect**. Authenticated connections. Authenticates only when the client establishes a relationship with a server.
- **Pkt Integrity**. Encrypted connections. Verifies that all data is received from the client and that it has not been changed in transit.
- **Pkt Privacy**. Signed encryption, supported only for XMLA. Verifies that all data is received from the client, that it has not been changed in transit, and protects the privacy of the data by encrypting it.

For more information, see [Establishing Secure Connections in ADOMD.NET](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-client/connections-in-adomd-net-establishing-secure-connections)

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

### Roles

Specify a comma-delimited list of predefined roles to connect to a server or database using permissions conveyed by that role. If this property is omitted, all roles are used, and the effective permissions are the combination of all roles. Setting the property to an empty value, for example, `Roles=' '` means the client connection has no role membership.

An administrator using this property connects using the permissions conveyed by the role. Some commands might fail if the role does not provide sufficient permission.

::: moniker-end

### SSPI

Explicitly specifies which security package to use for client authentication when **Integrated Security** is set to **SSPI**. SSPI supports multiple packages, but you can use this property to specify a particular package. Valid values are:

- **Negotiate**
- **Kerberos**
- **NTLM**
- **Anonymous User**

If this property is not set, all packages will be available to the connection.

### Use Encryption for Data

Encrypts data transmissions. Valid values are True or False.

### User ID=...; Password=

The User ID and Password properties are used to provide the appropriate credentials to the server, when the currently active user in the client application cannot be automatically propagated to the server. The behavior depends on the transport protocol and the server being connected to:

- When connecting over TCP to SSAS, the client library will impersonate the Windows user using the specified username and password, and then connect as usual to the server. 
- When connecting over HTTP(S) to SSAS, the credentials are provided to the web server based on the authentication mode configured on the web server (e.g. Basic auth or Windows auth), and the web server will perform the appropriate Windows impersonation before connecting to the SSAS server. Therefore, the correct credentials will flow to the server.
- When connecting to Azure AS or Power BI Premium, the User ID and Password are used to obtain an Azure Active Directory (AAD) token which is then presented to the service during authentication. AAD may also require MFA (multi-factor authentication) and this can cause additional user interaction before the token can be generated.

**Note:** "User ID" has an embedded space. An alternate alias for User ID is UID and an alternate alias for Password is PWD.  


## See also

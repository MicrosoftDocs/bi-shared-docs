---
title: "Connection string properties (Analysis Services) | Microsoft Docs"
description: Learn about connection string properties used to query Azure Analysis Services, SQL Server Analysis Services, and Power BI Premium dataset data.
ms.date: 11/25/2020
ms.prod: sql
ms.technology: analysis-services
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.custom: contperfq4
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Connection string properties

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

This article describes connection string properties used by client applications that connect to and query Azure Analysis Services (Azure AS), SQL Server Analysis Services (SSAS), and Power BI Premium dataset data. These properties are used by the Analysis Services client libraries, ADOMD.NET, AMO, and OLE DB (MSOLAP) provider for Analysis Services. The majority of connection string properties can be used with all three client libraries. Exceptions are called out in the description.

Use the **Version** selector above the table of contents to the left to see only those properties that apply to a particular platform or version.

## Connection properties

### Data Source

Specifies the server instance. This property is required for all connections.

::: moniker range="asallproducts-allversions || azure-analysis-services-current"

Valid values for Azure Analysis Services include `<protocol>://<region>/<servername>` where protocol is string `asazure` or `link` when using a [server name alias](https://docs.microsoft.com/azure/analysis-services/analysis-services-server-alias), region is the Uri where the server was created (for example, westus.asazure.windows.net), and servername is the name of your unique server within the region.

|Example  |Description  |
|---------|---------|
|`Data source=asazure://westus.asazure.windows.net/myasserver`|Azure Analysis Services.|
|`Data source=link://friendlyname.salesapp.azurewebsites.net/`|Azure Analysis Services using server name alias.|

::: moniker-end

::: moniker range="asallproducts-allversions || power-bi-premium-current"

Valid values for Power BI Premium include `<protocol>://api.powerbi.com/v1.0/[tenant name]/[workspace name]` where protocol is string `powerbi`, Uri is `api.powerbi.com`, tenant name is the organization tenant name or `myorg`, and workspace name is the name of a workspace assigned to a dedicated capacity.

|Example  |Description  |
|---------|---------|
|`Data source=powerbi://api.powerbi.com/v1.0/contoso.com/Sales Workspace`|Power BI Premium workspace.|

::: moniker-end

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

Valid values for SQL Server Analysis Services include the network name or IP address of the server, local or localhost for local connections, a URL if the server is configured for HTTP or HTTPS access, or the name of a local cube (.cub) file.

|Example  |Description  |
|---------|---------|
|`Data source=AW-SRV01`     |  SSAS default instance and port (TCP 2383).       |
|`Data source=AW-SRV01\Finance`     |  SSAS named instance.       |
|`Data source=AW-SRV01:8081`     |   SSAS default instance, specified port.      |
|`Data source=AW-SRV01.corp.Adventure-Works.com`    |    SSAS fully qualified domain name, default instance and port.     |
|`Data source=172.16.254.1`     |   SSAS IP address of the server, bypassing DNS server lookup. Useful for troubleshooting connection problems.      |

::: moniker-end

### Initial Catalog or Catalog

Specifies the name of the Analysis Services database or Power BI Premium dataset to connect to. The database must be deployed on Analysis Services or a Power BI Premium workspace and you must have permission to connect to it. For SSAS, the first allowed database is automatically selected. For Azure AS and Power BI Premium, a database is not automatically selected, but a catalog can be specified using the Catalog property after opening the connection. This property is optional for AMO and ADOMD.NET connections.

|Example  |Description  |
|---------|---------|
|`Initial catalog=AdventureWorks`| Database or dataset name|

### Provider

This property is required on the connection string when using an OLE DB provider like MSOLAP. It allows you to use either a version independent provider (usually the latest) like "Provider=MSOLAP", or you can also specify a version dependent provider like "Provider=MSOLAP.7". Valid version dependent values follow the pattern MSOLAP.\<version>, where \<version> is either 7 or 8. For example, MSOLAP.7 released in SQL Server 2016. Version ".8" is the latest and considered "evergreen". It's expected to keep updating with backward compatibility maintained. Earlier version numbers are also possible, but those releases of MSOLAP are now out of standard support.

This property is optional for ADOMD.NET and AMO. It's allowed for convenience when copying an MSOLAP connection string to use with ADOMD.NET and AMO.

|Example  |Description  |
|---------|---------|
|`Provider=MSOLAP.7`|Connections requiring SQL Server 2016 version of the OLE DB provider for Analysis Services.|

### Cube

Cube name or perspective name. A database can contain multiple cubes and perspectives. When multiple targets are possible, include the cube or perspective name on the connection string.

|Example  |Description  |
|---------|---------|
|`Cube=Sales`|A cube named Sales.|
|`Cube=SalesPerspective`|A perspective named SalesPerspective.|

## Authentication and security properties

::: moniker range="asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current"

Azure Analysis Services and Power BI Premium use Azure Active Directory - Universal with MFA (recommended), Azure Active Directory authentication with username and password, Azure Active Directory access tokens, or Windows authentication.

::: moniker-end

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

SQL Server Analysis Services uses Windows authentication only, but you can set properties on the connection string to pass in a specific user name and password.

::: moniker-end
  
Properties are listed in alphabetical order.

::: moniker range="asallproducts-allversions || azure-analysis-services-current || >= sql-analysis-services-2016"

### EffectiveUserName

Use when an end user identity must be impersonated on the server. For SSAS, specify in a domain\user format. For Azure AS, specify in UPN format. To use this property, the caller must have administrative permissions in Analysis Services.

::: moniker-end

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

### Encrypt Password

Specifies whether a local password is to be used to encrypt local cubes. Valid values are **True** or **False**. The default is False.

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

The Windows identity of the caller is used to connect to Analysis Services. Valid values are  **SSPI**, **blank**, **Basic**, and **ClaimsToken***.

SSPI is the default value for TCP connections, allowing NTLM, Kerberos, or Anonymous authentication. For Azure AS and Power BI Premium **SSPI** indicates AD Translation. When using SSPI, **ProtectionLevel** property must be set to Connect, Pkt Integrity, or Pkt Privacy.

blank is the default value for HTTP connections.

*ClaimsToken is supported for Azure AS and Power BI Premium.

### Persist Security Info

Valid values are **True** or **False**. When set to True, security information, such as the user identity or password previously specified on the connection string, can be obtained from the connection after the connection is made. The default value is False.

### Protection Level

Determines the security level used on the connection. Values supported depend on the underlying transport. Valid values are:

- **None**. Unauthenticated or anonymous connections. Performs no authentication on data sent to the server.
- **Connect**. Authenticated connections. Authenticates only when the client establishes a relationship with a server.
- **Pkt Integrity**. Encrypted connections. Verifies that all data is received from the client and that it has not been changed in transit.
- **Pkt Privacy**. Signed encryption, supported only for TCP. Verifies that all data is received from the client, that it has not been changed in transit, and protects the privacy of the data by encrypting it.

To learn more, see [Establishing Secure Connections in ADOMD.NET](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-client/connections-in-adomd-net-establishing-secure-connections)

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

Encrypts data transmissions. Valid values are **True** or **False**.

### User ID=...; Password=

User ID and Password properties provide the appropriate credentials to the server when the current active user in the client application cannot be automatically propagated to the server. The behavior depends on the transport protocol and the server being connected to:

- When connecting over TCP to SSAS, the client library will impersonate the Windows user using the specified username and password, and then connect as usual to the server.
- When connecting over HTTP(S) to SSAS, the credentials are provided to the web server based on the authentication mode configured on the web server, for example Basic auth or Windows auth. The web server will perform the appropriate Windows impersonation before connecting to the SSAS server, therefore providing the correct credentials flow to the server.
- When connecting to Azure AS or Power BI Premium, the User ID and Password are used to obtain an Azure Active Directory (AAD) token which is then presented to the service during authentication. AAD may also require multi-factor authentication (MFA), which can require additional user interaction before the token can be generated.
- If you've already acquired a valid AAD access token from your own application (user, Service Principal, or [Managed identity for Azure resources](/azure/active-directory/managed-identities-azure-resources/overview), you can omit the **User ID** property and specify the access token in the **Password** property. This is supported for access tokens acquired interactively for a user, as well as using the [OAuth 2.0 On-Behalf-Of flow](/azure/active-directory/develop/v2-oauth2-on-behalf-of-flow) (for example, a middle-tier web application connecting to Analysis Services on behalf of the user).

**Note:** "User ID" has an embedded space. An alternate alias for User ID is **UID** and an alternate alias for Password is **PWD**.  

## Special purpose properties

 These properties are used to ensure specific connection behaviors required by an application. Properties are listed in alphabetical order.  

### Application Name

Sets the name of the application associated with the connection. This value can be useful when monitoring tracing events, especially when you have several applications accessing the same databases. For example, adding Application Name='test' to a connection string causes 'test' to appear in a SQL Server Profiler trace. Aliases for this property include **SspropInitAppName**, **AppName**. To learn more, see [Application Name for SQL Server Connections](https://www.connectionstrings.com/use-application-name-sql-server/).

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

### Auto Synch Period

Sets the frequency (in milliseconds) of client and server cache synchronization. ADOMD.NET provides client caching for frequently used objects that have minimal memory overhead. This helps reduce the number of round trips to the server. The default is 10000 milliseconds (or 10 seconds). When set to null or 0, automatic synchronization is turned off.

For performance reasons, the client libraries cache some information from the server, for example, certain schema rowsets. Auto Synch Period allows a user to change the time period after which the client library checks with the server whether or not the caches need to be emptied. In general, you should not need to change the value from default.

::: moniker-end

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

### Character Encoding

Defines how characters are encoded on the request. Valid values are **Default** or **UTF-8** (these are equivalent), and **UTF-16**.

::: moniker-end

### CommitTimeout

An XMLA property. Determines how long, in milliseconds, the commit phase of a currently running command waits before rolling back. When greater than 0, overrides the value of the corresponding CommitTimeout property in the server configuration.

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

### CompareCaseSensitiveStringFlags

Adjusts case-sensitive string comparisons for a specified locale.

::: moniker-end

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

### Compression Level

If **TransportCompression** is compressed, you can set the compression level to control how much compression is used. Valid values are **0** through **9**, with 0 having least compression, and 9 having the most compression. Increased compression slows performance. The default value is 0.

::: moniker-end

### Connect Timeout

Determines the maximum amount of time (in seconds) the client attempts a connection before timing out. If a connection does not succeed within this period, the client quits trying to connect and generates an error.

### DbpropMsmdRequestMemoryLimit

Overrides the [Memory\QueryMemoryLimit](../server-properties/memory-properties.md) server property value for a connection.

Specified in kilobytes, this property can *reduce* the amount of memory used during a query from the maximum allowed memory (specified as a percentage) in QueryMemoryLimit. It cannot increase the amount of memory used beyond the maximum allowed memory specified in QueryMemoryLimit.

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

### Default MDX Visual Mode

Set this property to control how members are aggregated when dimension security is applied.

For cube data that everyone is allowed to see, aggregating all of the members makes sense because all of the values that contribute to the total are visible. However, if you filter or restrict dimensions based on user identity, showing a total based on all the members (combining both restricted and allowed values into a single total) might be confusing or show more information than should be revealed.

To specify how members are aggregated when dimension security is applied, you can set this property to True to use only allowed values in the aggregation, or False to exclude restricted values from the total.

When set on the connection string, this value applies to the cube or perspective level. Within a model, you can control visual totals at a more granular level.

Valid values are,

- **0** is the default. Currently, the default behavior is equivalent to 2, where aggregations include values that are hidden from the user.
- **1** excludes hidden values from the total. This is the default for Excel.
- **2** includes hidden values in the total. This is the default value on the server.

The alias for this property is **VisualMode**.

::: moniker-end

### MDX Compatibility

The purpose of this property is to ensure a consistent set of MDX behaviors for applications that issue MDX queries. Excel, which uses MDX queries to populate and calculate a PivotTable connected to Analysis Services, sets this property to 1, to ensure that placeholder members in ragged hierarchies are visible in a PivotTable. Valid values include 0, 1, 2.

0 and 1 expose placeholder members; 2 does not. If this is empty, 0 is assumed.

### MDX Missing Member Mode

Indicates whether missing members are ignored in MDX statements. Valid values are **Default**, **Error**, and **Ignore**. Default uses a server-defined value. Error generates an error when a member does not exist. Ignore specifies that missing values should be ignored.

### Optimize Response

A bitmask indicating which of the following query response optimizations are enabled.

- 0x01 Use the NormalTupleSet (default).
- 0x02 Use when slicers are empty.

### Packet Size

Applies to TCP connections only. A network packet size (in bytes) between 512 and 32,767. The default network packet size is 4096.

### Protocol Format

Sets the format of the XML used by the XMLA communication protocol. Valid values are **Default**, **XML**, or **Binary**. You can specify the XML be sent in a binary format or as text XML. Binary format encodes XML elements and attributes, making them smaller. In addition, compression can also be enabled for the messages to reduce the size of requests and responses using the Transport Compression option. Requests and responses can use different protocol formats depending on what the client and server supports. For example, a client library may only support binary for responses, but not for requests, or a server may have disabled binary for incoming requests.

OLE DB provider can format requests and responses in binary or compressed format. AMO and ADOMD.NET format the requests as Text, but accept responses in binary or compressed format.

This connection string property is equivalent to the **EnableBinaryXML** and **EnableCompression** server configuration settings.

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

### Real Time Olap

Set this property to bypass caching, causing all storage queries to fetch data from the source system. By default, this property is not set.

::: moniker-end

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

### Safety Options

Sets the safety level for user-defined functions and actions. Valid values are **0**, **1**, **2**. In an Excel connection, this property is Safety Options=2. Details about this option can be found in <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A>.

::: moniker-end

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

### SQLQueryMode

Specifies whether SQL queries include calculations. Valid values are **Data**, Calculated, **IncludeEmpty**. Data means that no calculations are allowed. Calculated allows calculations. IncludeEmpty allows calculations and empty rows to be returned in the query result.

::: moniker-end

### Timeout

Specifies how long (in seconds) the client library waits for a command to complete before generating an error.

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

### Transport Compression

Defines how client and server communications are compressed. Valid values are **Default**, **None**, **Compressed**. None indicates no compression is used. Compressed uses XPRESS compression.

::: moniker-end

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

### UseExistingFile

Used when connecting to a local cube. This property specifies whether the local cube is overwritten. Valid values are **True** or **False**. If set to True, the cube file must exist. The existing file will be the target of the connection. If set to False, the cube file is overwritten.

::: moniker-end

## See also

[AMO Fundamental Classes - Server objects](../amo/amo-fundamental-classes.md#server-objects)  
[AdomdConnection Class - Properties](https://docs.microsoft.com/dotnet/api/microsoft.analysisservices.adomdclient.adomdconnection?view=analysisservices-dotnet&preserve-view=true#properties)

---
title: "ADOMD.NET Server Functionality | Microsoft Docs"
description: Learn how to use ADOMD.NET server objects to create a user defined function (UDF) or a stored procedure for Microsoft SQL Server Analysis Services.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: adomd
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# ADOMD.NET Server Functionality
  All ADOMD.NET server objects provide read-only access to the data and metadata on the server. To retrieve data and metadata, you use the ADOMD.NET server object model as the server object model does not support schema rowsets.  
  
 With ADOMD.NET server objects, you can create a user defined function (UDF) or a stored procedure for Microsoft SQL Server Analysis Services. These in-process methods are called through query statements created in languages such as Multidimensional Expressions (MDX), Data Mining Extensions (DMX), or SQL. These in-process methods also provide added functionality without the latencies associated with network communications.  
  
> [!NOTE]  
>  The Microsoft.AnalysisServices.AdomdServer.AdomdCommand object only supports DMX.  
  
## What is a UDF?  
 A *UDF* is a method that has the following characteristics:  
  
-   You can call the UDF in the context of a query.  
  
-   The UDF can take any number of parameters.  
  
-   The UDF can return various types of data.  
  
 The following example uses the fictional UDF, `FinalSalesNumber`:  
  
```sql  
SELECT SalesPerson.Name ON ROWS,  
       FinalSalesNumber() ON COLUMNS  
FROM SalesModel  
```  
  
## What is a Stored Procedure?  
 A *stored procedure* is a method that has the following characteristics:  
  
-   You call a stored procedure on its own with the MDX `CALL` statement.  
  
-   A stored procedure can take any number of parameters.  
  
-   A stored procedure can return a dataset, an **IDataReader**, or an empty result.  
  
 The following example uses the fictional stored procedure, `FinalSalesNumbers`:  
  
```sql 
CALL FinalSalesNumbers()  
```  
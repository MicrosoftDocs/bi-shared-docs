---
title: "TableBinding Data Type (ASSL) | Microsoft Docs"
description: Learn about the TableBinding data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# TableBinding Data Type (ASSL)

  Defines a derived data type that represents a binding to a table.  
  
## Syntax  
  
```xml  
  
<TableBinding>  
   <!-- The following elements extend TabularBinding -->  
   <DataSourceID>...</DataSourceID>  
   <DbTableName>...</DbTableName>  
   <DbSchemaName>...</DbSchemaName>  
</TableBinding>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[TabularBinding](tabularbinding-data-type-assl.md)|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[DataSourceID](../properties/datasourceid-element-assl.md), [DbSchemaName](../properties/dbschemaname-element-assl.md), [DbTableName](../properties/dbtablename-element-assl.md)|  
|Derived elements|See [Binding](binding-data-type-assl.md)|  
  
## Remarks  
 Note that referencing other tables in the filter expression by use of a subselect could have performance implications in some data sources. However, the designer can totally control the SQL expression by defining a named query in the data source view, and then referencing that.  
  
 The method of defining the bindings for a partition are independent of the use of partitioned tables in the data source view.  
  
 As an example, consider a measure group whose default table is "Sales," with columns Date, Product ID, Qty, Price, and Amount (calculated in the data source view). Then the partition "Sales97" could use the table "Sales97" with filter "Year(Sales.Date) = 97."  
  
 The effective query is:  
  
```sql  
SELECT Date, Product ID, Qty, Price, Qty * Price AS Amount   
   FROM Sales97 As Sales  
   WHERE Year(Sales.Date) = 97  
```  
  
 The calculated expression still applies, even if the expression used qualified table names (for example, Sales.Qty). The same applies if instead the table were replaced by some query "SELECT…" The FROM clause above would become "FROM SELECT ... As Sales."  
  
 For more information about the **Binding** type, including tables of Analysis Services Scripting Language (ASSL) objects of type **Binding** and the inheritance hierarchy of **Binding** types, see [Binding Data Type &#40;ASSL&#41;](binding-data-type-assl.md).  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.TableBinding>.  
  
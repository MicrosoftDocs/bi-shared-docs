---
title: "DAX in Analysis Services tabular models | Microsoft Docs"
description: Learn that for tabular models, DAX formulas are used in calculated columns, measures, and row filters.
ms.date: 04/20/2020
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# DAX in tabular models

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

Data Analysis Expressions (DAX) is a formula language used to create custom calculations in Analysis Services, Power BI, and Power Pivot in Excel. DAX formulas include functions, operators, and values to perform advanced calculations on data in tables and columns.  
  
While DAX is used in Analysis Services, Power BI, and Power Pivot in Excel, this article applies more to Analysis Services tabular model projects authored in Visual Studio.  
  
## DAX formulas in calculated columns, calculated tables, measures, and row filters  

 For tabular models, DAX formulas are used in calculated columns, measures, and row filters.  
  
### Calculated columns  

A calculated column is a column that you add to an existing table (in the model designer) and then create a DAX formula that defines the column's values.
  
> [!NOTE]  
> Calculated columns are not supported for models that retrieve data from a relational data source using DirectQuery mode.  
  
When a calculated column contains a valid DAX formula, values are calculated for each row as soon as the formula is entered. Values are then stored in the database. For example, in a Date table, when the formula `=[Calendar Year] & " Q" & [Calendar Quarter]` is entered into the formula bar, a value for each row in the table is calculated by taking values from the Calendar Year column (in the same Date table), adding a space and the capital letter Q, and then adding the values from the Calendar Quarter column (in the same Date table). The result for each row in the calculated column is calculated immediately and appears, for example, as **2010 Q1**. Column values are only recalculated if the data is re-processed.  
  
To learn more, see [Calculated Columns](../../analysis-services/tabular-models/ssas-calculated-columns.md).  

### Calculated tables

Calculated tables are computed objects, based on either a DAX query or expression, derived from all or part of other tables in the same model.

To learn more, see [Calculated tables](../../analysis-services/tabular-models/create-a-calculated-table-ssas-tabular.md).

### Measures  

Measures are dynamic formulas where the results change depending on context. Measures are used in reporting formats that support combining and filtering model data by using multiple attributes such as a Power BI report or Excel PivotTable or PivotChart. Measures are defined by the model author by using the measure grid (and formula bar) in the model designer in Visual Studio.  
  
A formula in a measure can use standard aggregation functions automatically created by using the Autosum feature, such as COUNT or SUM, or you can define your own formula by using DAX. When you define a formula for a measure in the formula bar, a Tooltip feature shows a preview of what the results would be for the total in the current context, but otherwise the results are not immediately output anywhere. Other measure details also appear in the **Properties** pane.  
  
The reason you cannot see the (filtered) results of the calculation immediately is because the result of a measure cannot be determined without context. To evaluate a measure requires a reporting client application that can provide the context needed to retrieve the data relevant to each cell and then evaluate the expression for each cell. That client might be an Excel PivotTable or PivotChart, a Power BI report, or an MDX query. Regardless of the reporting client, a separate query is run for each cell in the results. That is to say, each combination of row and column headers in a PivotTable, or each selection of slicers and filters in a Power BI report, generates a different subset of data over which the measure is calculated. For example, in a measure with the formula, `Total Sales:=SUM([Sales Amount])`, when a user places the TotalSales measure in the Values window in a PivotTable, and then places the DimProductCategory column from a DimProduct table into the Filters window, the sum of Sales Amount is calculated and displayed for each product category.  
  
Unlike calculated columns and row filters, the syntax for a measure includes the measure's name preceding the formula. In the example just provided, the name **Total Sales:** appears preceding the formula. After you have created a measure, the name and its definition appear in the reporting client application Field List and depending on perspectives and roles is available to all users of the model.  
  
To learn more, see [Measures](../../analysis-services/tabular-models/measures-ssas-tabular.md).  
  
### Row filters  

Row filters define which rows in a table are visible to members of a particular role. Row filters can be created for each table in a model by using DAX formulas. Row filters are created for a particular role by using Role Manager in Visual Studio. Row filters can also be defined for a deployed model by using Role Properties in SQL Server Management Studio (SSMS).  
  
In a row filter, a DAX formula, which must evaluate to a Boolean TRUE/FALSE condition, defines which rows can be returned by the results of a query by members of that particular role. Rows not included in the DAX formula cannot be returned. For example, for members of the Sales role, the Customers table with the following DAX formula, `=Customers[Country] = "USA"`, members of the Sales role will only be able to view data for customers in the USA, and aggregates, such as SUM are returned only for customers in the USA.  
  
When you define a row filter by using DAX formula, you are creating an allowed row set. This does not deny access to other rows; rather, they are simply not returned as part of the allowed row set. Other roles can allow access to the rows excluded by the DAX formula. If a user is a member of another role, and that role's row filters allow access to that particular row set, the user can view data for that row.  
  
Row filters apply to the specified rows as well as related rows. When a table has multiple relationships, filters apply security for the relationship that is active. Row filters will be intersected with other row filters defined for related tables.  
  
To learn more, see [Roles](../../analysis-services/tabular-models/roles-ssas-tabular.md).  
  
## DAX data types  

You can import data into a model from many different data sources that might support different data types. When you import data into a model, the data is converted to one of the tabular model data types. When the model data is used in a calculation, the data is then converted to a DAX data type for the duration and output of the calculation. When you create a DAX formula, the terms used in the formula will automatically determine the value data type returned.  
  
Tabular models, and DAX, support the following data types:  
  
|Data type in model|Data type in DAX|Description|  
|------------------------|----------------------|-----------------|  
|Whole Number|A 64 bit (eight-bytes) integer value <sup>1, 2</sup>|Numbers that have no decimal places. Integers can be positive or negative numbers, but must be whole numbers between -9,223,372,036,854,775,808 (-2^63) and 9,223,372,036,854,775,807 (2^63-1).|  
|Decimal Number|A 64 bit (eight-bytes) real number <sup>1, 2</sup>|Real numbers are numbers that can have decimal places. Real numbers cover a wide range of values:<br /><br /> Negative values from -1.79E +308 through -2.23E -308<br /><br /> Zero<br /><br /> Positive values from 2.23E -308 through 1.79E + 308<br /><br /> However, the number of significant digits is limited to 17 decimal digits.|  
|Boolean|Boolean|Either a True or False value.|  
|Text|String|A Unicode character data string. Can be strings, numbers or dates represented in a text format.|  
|Date|Date/time|Dates and times in an accepted date-time representation.<br /><br /> Valid dates are all dates after March 1, 1900.|  
|Currency|Currency|Currency data type allows values between -922,337,203,685,477.5808 to 922,337,203,685,477.5807 with four decimal digits of fixed precision.|  
|N/A|Blank|A blank is a data type in DAX that represents and replaces SQL nulls. You can create a blank by using the BLANK function, and test for blanks by using the logical function, ISBLANK.|  
  
Tabular models also include the Table data type as the input or output to many DAX functions. For example, the FILTER function takes a table as input and outputs another table that contains only the rows that meet the filter conditions. By combining table functions with aggregation functions, you can perform complex calculations over dynamically defined data sets.  
  
While data types are typically automatically set, it is important to understand data types and how they apply, in-particular, to DAX formulas. Errors in formulas or unexpected results, for example, are often caused by using a particular operator that cannot be used with a data type specified in an argument. For example, the formula, `= 1 & 2`, returns a string result of 12. The formula, `= "1" + "2"`, however, returns an integer result of 3.  
  
For detailed information about data types in tabular models and explicit and implicit conversions of data types in DAX, see [Data types supported](../../analysis-services/tabular-models/data-types-supported-ssas-tabular.md).  
  
## DAX operators  

The DAX language uses four different types of calculation operators in formulas:  

- Comparison operators to compare values and return a logical TRUE\FALSE value.  
- Arithmetic operators to perform arithmetic calculations that return numeric values.  
- Text concatenation operators to join two or more text strings.  
- Logical operators that combine two or more expressions to return a single result.  
  
For detailed information about operators used in DAX formulas, see [DAX Operator Reference](/dax/dax-operator-reference).  
  
## DAX formulas  

DAX formulas are essential for creating calculations in calculated columns and measures, and securing your data by using row level filters. To create formulas for calculated columns and measures, you will use the formula bar along the top of the model designer window or the DAX Editor. To create formulas for row filters, you will use the Role Manager dialog box. Information in this section is meant to get you started with understanding the basics of DAX formulas.  
  
### Formula basics  

DAX enables tabular model authors to define custom calculations in both model tables, as part of calculated columns, and as measures associated with tables, but not appearing directly in them. DAX also enables model authors to secure data, by creating calculations that return a Boolean value defining which rows in a particular or related table can be queried by member users of the associated role.  
  
DAX formulas can be very simple or quite complex. The following table shows some examples of simple formulas that could be used in a calculated column.  
  
| Formula | Description |
| ------- | ----------- |
|`=TODAY()`|Inserts today's date in every row of the column.|  
|`=3`|Inserts the value 3 in every row of the column.|  
|`=[Column1] + [Column2]`|Adds the values in the same row of [Column1] and [Column2] and puts the results in the calculated column of the same row.|  
  
Whether the formula you create is simple or complex, you can use the following steps when building a formula:  
  
1. Each formula must begin with an equal sign.  
  
1. You can either type or select a function name, or type an expression.  
  
1. Begin to type the first few letters of the function or name you want, and AutoComplete displays a list of available functions, tables, and columns. Press TAB to add an item from the AutoComplete list to the formula.  
  
    You can also click the **Fx** button to display a list of available functions. To select a function from the dropdown list, use the arrow keys to highlight the item, and click **OK** to add the function to the formula.  
  
1. Supply the arguments to the function by selecting them from a dropdown list of possible tables and columns, or by typing in values.  
  
1. Check for syntax errors: ensure that all parentheses are closed and columns, tables and values are referenced correctly.  
  
1. Press ENTER to accept the formula.  
  
> [!NOTE]  
> In a calculated column, as soon as you enter the formula and the formula is validated, the column is populated with values. In a measure, pressing ENTER saves the measure definition in the measure grid with the table. If a formula is invalid, an error will be displayed.  
  
 In this example, we will look at a more complex formula in a measure named Days in Current Quarter:  
  
```dax
Days in Current Quarter:=COUNTROWS( DATESBETWEEN( 'Date'[Date], STARTOFQUARTER( LASTDATE('Date'[Date])), ENDOFQUARTER('Date'[Date])))  
```  
  
This measure is used to create a comparison ratio between an incomplete period and the previous period. The formula must take into account the proportion of the period that has elapsed, and compare it to the same proportion in the previous period. In this case, [Days Current Quarter to Date]/[Days in Current Quarter] gives the proportion elapsed in the current period.  
  
This formula contains the following elements:  
  
|Formula element|Description|  
|---------------------|-----------------|  
|`Days in Current Quarter:=`|The name of the measure.|  
|`=`|The equals sign (=) begins the formula.|  
|`COUNTROWS`|The COUNTROWS function counts the number of rows in the Date table|  
|`()`|Open and closing parenthesis specifies arguments.|  
|`DATESBETWEEN`|The DATESBETWEEN function returns the dates between the last date for each value in the Date column in the Date table.|  
|`'Date'`|Specifies the Date table. Tables are in single quotes.|  
|`[Date]`|Specifies the Date column in the Date table. Columns are in brackets.|  
|`,`||  
|`STARTOFQUARTER`|The STARTOFQUARTER function returns the date of the start of the quarter.|  
|`LASTDATE`|The LASTDATE function returns the last date of the quarter.|  
|`'Date'`|Specifies the Date table.|  
|`[Date]`|Specifies the Date column in the Date table.|  
|`,`||  
|`ENDOFQUARTER`|The ENDOFQUARTER function|  
|`'Date'`|Specifies the Date table.|  
|`[Date]`|Specifies the Date column in the Date table.|  
  
#### Using formula AutoComplete  

Both the formula bar in the model designer and the formula Row Filters window in the Role Manager dialog box provide an AutoComplete feature. AutoComplete helps you enter a valid formula syntax by providing you with options for each element in the formula.  
  
- You can use formula AutoComplete in the middle of an existing formula with nested functions. The text immediately before the insertion point is used to display values in the drop-down list, and all of the text after the insertion point remains unchanged.  
  
- AutoComplete does not add the closing parenthesis of functions or automatically match parentheses. You must make sure that each function is syntactically correct or you cannot save or use the formula.  
  
#### Using multiple functions in a formula  

You can nest functions, meaning that you use the results from one function as an argument of another function. You can nest up to 64 levels of functions in calculated columns. However, nesting can make it difficult to create or troubleshoot formulas.  
  
Many functions are designed to be used solely as nested functions. These functions return a table, which cannot be directly saved as a result; it must be provided as input to a table function. For example, the functions SUMX, AVERAGEX, and MINX all require a table as the first argument.  
  
> [!NOTE]  
> Some limits are applied within measures on nesting of functions to ensure that performance is not affected by the many calculations required by dependencies among columns.  
  
## DAX functions  

This section provides an overview of the *types* of functions supported in DAX. For more detailed information, see [DAX Function Reference](/dax/data-analysis-expressions-dax-reference).  
  
DAX provides a variety of functions you can use perform calculations using dates and times, create conditional values, work with strings, perform lookups based on relationships, and the ability to iterate over a table to perform recursive calculations. If you are familiar with Excel formulas, many of these functions will appear very similar; however, DAX formulas are different in the following important ways:  
  
- A DAX function always references a complete column or a table. If you want to use only particular values from a table or column, you can add filters to the formula.  
  
- If you need to customize calculations on a row-by-row basis, DAX provides functions that let you use the current row value or a related value as a kind of parameter, to perform calculations that vary by context. To understand how these functions work, see Context in DAX Formulas later in this article.  
  
- DAX includes many functions that return a table, rather than a value. The table is not displayed in a reporting client, but is used to provide input to other functions. For example, you can retrieve a table and then count the distinct values in it, or calculate dynamic sums across filtered tables or columns.  
  
- DAX functions include a variety of *time intelligence* functions. These functions let you define or select date ranges, and perform dynamic calculations based on these dates or range. For example, you can compare sums across parallel periods.  
  
### Date and time functions  

The date and time functions in DAX are similar to date and time functions in Microsoft Excel. However, DAX functions are based on the **datetime** data types used by Microsoft SQL Server. To learn more, see [Date and Time Functions (DAX)](/dax/date-and-time-functions-dax).  
  
### Filter functions  

The filter functions in DAX return specific data types, look up values in related tales, and filter by related values. The lookup functions work by using tables and relationships, like a database. The filtering functions let you manipulate data context to create dynamic calculations. To learn more, see [Filter Functions (DAX)](/dax/filter-functions-dax).  
  
### Information functions  

An information function looks at the cell or row that is provided as an argument and tells you whether the value matches the expected type. For example, the ISERROR function returns TRUE if the value that you reference contains an error. To learn more, see [Information Functions (DAX)](/dax/information-functions-dax).  
  
### Logical functions  

Logical functions act upon an expression to return information about the values in the expression. For example, the TRUE function lets you know whether an expression that you are evaluating returns a TRUE value. To learn more, see [Logical Functions (DAX)](/dax/logical-functions-dax).  
  
### Mathematical and trigonometric functions  

The mathematical functions in DAX are very similar to the Excel mathematical and trigonometric functions. Some minor differences exist in the numeric data types used by DAX functions. To learn more, see [Math and Trig Functions (DAX)](/dax/math-and-trig-functions-dax).  

### Other functions  

These functions perform unique actions that cannot be defined by any of the categories most other functions belong to. To learn more, see [Other Functions (DAX)](/dax/other-functions-dax).
  
### Statistical functions  

DAX provides statistical functions that perform aggregations. In addition to creating sums and averages, or finding the minimum and maximum values, in DAX you can also filter a column before aggregating or create aggregations based on related tables. To learn more, see [Statistical Functions (DAX)](/dax/statistical-functions-dax).  
  
### Text functions  

The text functions in DAX are very similar to their counterparts in Excel. You can return part of a string, search for text within a string, or concatenate string values. DAX also provides functions for controlling the formats for dates, times, and numbers. To learn more, see [Text Functions (DAX)](/dax/text-functions-dax).  
  
### Time intelligence functions  

The time intelligence functions provided in DAX let you create calculations that use built-in knowledge about calendars and dates. By using time and date ranges in combination with aggregations or calculations, you can build meaningful comparisons across comparable time periods for sales, inventory, and so on. To learn more, see [Time intelligence Functions (DAX)](/dax/time-intelligence-functions-dax).  
  
### Table-valued functions  

There are DAX functions that output tables, take tables as input, or do both. Because a table can have a single column, table-valued functions also take single columns as inputs. Understanding how to use these table-valued functions is important for fully utilizing DAX formulas. DAX includes the following types of table-valued functions:  
  
**Filter functions** - Return a column, table, or values related to the current row.  

**Aggregation functions** - Aggregate any expression over the rows of a table.  

**Time intelligence functions** - Return a table of dates, or use a table of dates to calculate an aggregation.  
  
## Context in DAX formulas  

*Context* is an important concept to understand when creating formulas using DAX. Context is what enables you to perform dynamic analysis, as the results of a formula change to reflect the current row or cell selection and also any related data. Understanding context and using context effectively are critical for building high-performing, dynamic analyses, and for troubleshooting problems in formulas.  
  
Formulas in tabular models can be evaluated in a different context, depending on other design elements:  
  
- Filters applied in a PivotTable or report  
  
- Filters defined within a formula  
  
- Relationships specified by using special functions within a formula  
  
 There are different types of context: *row context*, *query context*, and *filter context*.  
  
### Row context  

*Row context* can be thought of as "the current row". If you create a formula in a calculated column, the row context for that formula includes the values from all columns in the current row. If the table is related to another table, the content also includes all the values from the other table that are related to the current row.  
  
For example, suppose you create a calculated column, `=[Freight] + [Tax]`, that adds together values from two columns, Freight and Tax, from the same table. This formula automatically gets only the values from the current row in the specified columns.  
  
Row context also follows any relationships that have been defined between tables, including relationships defined within a calculated column by using DAX formulas, to determine which rows in related tables are associated with the current row.  
  
For example, the following formula uses the RELATED function to fetch a tax value from a related table, based on the region that the order was shipped to. The tax value is determined by using the value for region in the current table, looking up the region in the related table, and then getting the tax rate for that region from the related table.  
  
```dax
= [Freight] + RELATED('Region'[TaxRate])  
```  
  
This formula gets the tax rate for the current region from the Region table and adds it to the value of the Freight column. In DAX formulas, you do not need to know or specify the specific relationship that connects the tables.  
  
#### Multiple row context  

DAX includes functions that iterate calculations over a table. These functions can have multiple current rows, each with its own row context.  In essence, these functions let you create formulas that perform operations recursively over an inner and outer loop.  
  
For example, suppose your model contains a **Products** table and a **Sales** table. Users might want to go through the entire sales table, which is full of transactions involving multiple products, and find the largest quantity ordered for each product in any one transaction.  
  
With DAX you can build a single formula that returns the correct value, and the results are automatically updated any time a user adds data to the tables.  
  
```dax
=MAXX(FILTER(Sales,[ProdKey]=EARLIER([ProdKey])),Sales[OrderQty])  
```  
  
For a detailed walkthrough of this formula, see the [EARLIER Function (DAX)](/dax/earlier-function-dax).  
  
To summarize, the EARLIER function stores the row context from the operation that preceded the current operation. At all times, the function stores in memory two sets of context: one set of context represents the current row for the inner loop of the formula, and another set of context represents the current row for the outer loop of the formula. DAX automatically feeds values between the two loops so that you can create complex aggregates.  
  
#### Query context  

*Query context* refers to the subset of data that is implicitly retrieved for a formula. When a user places a measure or other value field into a PivotTable or into a report based on a tabular model, the engine examines the row and column headers, Slicers, and report filters to determine the context. Then, the necessary queries are run against the data source to get the correct subset of data, make the calculations defined by the formula, and then populate each cell in the PivotTable or report. The set of data that is retrieved is the query context for each cell.  
  
> [!WARNING]  
> For a model in DirectQuery mode, the context is evaluated, and then the set operations to retrieve the correct subset of data and calculate the results are translated to SQL statements. Those statements are then directly run against the relational data store. Therefore, although the method of getting the data and calculating the results is different, the context itself does not change.  
  
Because context changes depending on where you place the formula, the results of the formula can also change.  
  
For example, suppose you create a formula that sums the values in the **Profit** column of the **Sales** table: `=SUM('Sales'[Profit])`.  If you use this formula in a calculated column within the **Sales** table, the results for the formula will be the same for the entire table, because the query context for the formula is always the entire data set of the **Sales** table. Results will have profit for all regions, all products, all years, and so on.  
  
However, users typically don't want to see the same result hundreds of times, but instead want to get the profit for a particular year, a particular country/region, a particular product, or some combination of these, and then get a grand total.  
  
In a PivotTable, context can be changed by adding or removing column and row headers and by adding or removing Slicers. Whenever users add column or row headings to the PivotTable, they change the query context in which the measure is evaluated. Slicing and filtering operations also affect context. Therefore, the same formula, used in a measure, is evaluated in a different *query context* for each cell.  
  
#### Filter context  

*Filter context* is the set of values allowed in each column, or in the values retrieved from a related table. Filters can be applied to the column in the designer, or in the presentation layer (reports and PivotTables). Filters can also be defined explicitly by filter expressions within the formula.  
  
Filter context is added when you specify filter constraints on the set of values allowed in a column or table, by using arguments to a formula. Filter context applies on top of other contexts, such as row context or query context.  
  
In tabular models, there are many ways to create filter context. Within the context of clients that can consume the model, such as Power BI reports, users can create filters on the fly by adding slicers or report filters on the row and column headings. You can also specify filter expressions directly within the formula, to specify related values, to filter tables that are used as inputs, or to dynamically get context for the values that are used in calculations. You can also completely clear or selectively clear the filters on particular columns. This is very useful when creating formulas that calculate grand totals.  
  
To learn more about how to create filters within formulas, see the [FILTER Function (DAX)](/dax/filter-function-dax).  
  
For an example of how filters can be cleared to create grand totals, see the [ALL Function (DAX)](/dax/all-function-dax).  
  
For examples of how to selectively clear and apply filters within formulas, see the [ALLEXCEPT Function (DAX)](/dax/allexcept-function-dax).  
  
#### Determining context in formulas  

When you create a DAX formula, the formula is first tested for valid syntax, and then tested to make sure the names of the columns and tables included in the formula can be found in the current context. If any column or table specified by the formula cannot be found, an error is returned.  
  
Context during validation (and recalculation operations) is determined as described in the preceding sections, by using the available tables in the model, any relationships between the tables, and any filters that have been applied.  
  
For example, if you have just imported some data into a new table and it is not related to any other tables (and you have not applied any filters), the *current context* is the entire set of columns in the table. If the table is linked by relationships to other tables, the current context includes the related tables. If you add a column from the table to a report that has Slicers and maybe some report filters, the context for the formula is the subset of data in each cell of the report.  
  
Context is a powerful concept that can also make it difficult to troubleshoot formulas. We recommend that you begin with simple formulas and relationships to see how context works. The following section provides some examples of how formulas use different types of context to dynamically return results.  
  
##### Examples of context in formulas  
  
The [RELATED Function (DAX)](/dax/related-function-dax) function expands the context of the current row to include values in a related column. This lets you perform lookups. The example in this article illustrates the interaction of filtering and row context.  
  
The [FILTER Function (DAX)](/dax/filter-function-dax) function lets you specify the rows to include in the current context. The examples in this article also illustrate how to embed filters within other functions that perform aggregates.  
  
The [ALL Function (DAX)](/dax/all-function-dax) function sets context within a formula. You can use it to override filters that are applied as result of query context.  
  
The [ALLEXCEPT Function (DAX)](/dax/allexcept-function-dax) function lets you remove all filters except one that you specify. Both articles include examples that walk you through building formulas and understanding complex contexts.  
  
The [EARLIER Function (DAX)](/dax/earlier-function-dax) and [EARLIEST Function (DAX)](/dax/earliest-function-dax) functions let you loop through tables by performing calculations, while referencing a value from an inner loop. If you are familiar with the concept of recursion and with inner and outer loops, you will appreciate the power that the EARLIER and EARLIEST functions provide. If you are new to these concepts, you should follow the steps in the example carefully to see how the inner and outer contexts are used in calculations.  
  
## Formulas and the tabular model  

The model designer in Visual Studio is an area where you can work with multiple tables of data and connect the tables in a tabular model. Within this model, tables are joined by relationships on columns with common values (keys). The tabular model lets you link values to columns in other tables and create more interesting calculations. Just as in a relational database, you can connect many levels of related tables and use columns from any of the tables in the results.  
  
For example, you can link a sales table, a products table, and a product categories table, and users can use various combinations of the columns in PivotTables and reports. Related fields can be used to filter connected tables, or to create calculations over subsets. (If you are not familiar with relational database and working with tables and joins, see [Relationships](../../analysis-services/tabular-models/relationships-ssas-tabular.md).)  
  
Tabular models support multiple relationships among tables. To avoid confusion or wrong results, only one relationship at a time is designated as the active relationship, but you can change the active relationship as necessary to traverse different connections in the data in calculations. The [USERELATIONSHIP Function (DAX)](/dax/userelationship-function-dax) can be used to specify one or more relationships to be used in a specific calculation.  
  
In a tabular model, you should observe these formula design rules:  
  
- When tables are connected by a relationship, you must ensure that the two columns used as keys have values that match. Referential integrity is not enforced, however; therefore it is possible to have non-matching values in a key column and still create a relationship. If this happens, you should be aware that blank values or non-matching values might affect the results of formulas.  
  
- When you link tables in your model by using relationships, you enlarge the scope, or *context*, in which your formulas are evaluated. Changes in context resulting from the addition of new tables, new relationships, or from changes in the active relationship can cause your results to change in ways that you might not anticipate. To learn more, see Context in DAX Formulas earlier in this article.  
  
## Working with tables and columns  

Tables in tabular models look like Excel tables, but are different in the way they work with data and with formulas:  
  
- Formulas work only with tables and columns, not with individual cells, range references, or arrays.  
  
- Formulas can use relationships to get values from related tables. The values that are retrieved are always related to the current row value.  
  
- You cannot have irregular or "ragged" data like you can in an Excel worksheet. Each row in a table must contain the same number of columns. However, you can have empty values in some columns. Excel data tables and tabular model data tables are not interchangeable.  
  
- Because a data type is set for each column, each value in that column must be of the same type.  
  
### Referring to tables and columns in formulas  

You can refer to any table and column by using its name. For example, the following formula illustrates how to refer to columns from two tables by using the *fully qualified* name:  
  
```dax
=SUM('New Sales'[Amount]) + SUM('Past Sales'[Amount])  
```  
  
When a formula is evaluated, the model designer first checks for general syntax, and then checks the names of columns and tables that you provide against possible columns and tables in the current context. If the name is ambiguous or if the column or table cannot be found, you will get an error on your formula (an #ERROR string instead of a data value in cells where the error occurs). To learn more about naming requirements for tables, columns, and other objects, see "Naming Requirements" in [DAX Syntax Reference](/dax/dax-syntax-reference).  
  
### Table relationships  

By creating relationships between tables, you gain the ability to look up data in another table and use related values to perform complex calculations. For example, you can use a calculated column to look up all the shipping records related to the current reseller, and then sum the shipping costs for each. In many cases, however, a relationship might not be necessary. You can use the LOOKUPVALUE function in a formula to return the value in *result_columnName* for the row that meets criteria specified in the *search_column* and *search_value* parameters.  
  
Many DAX functions require that a relationship exist between the tables, or among multiple tables, in order to locate the columns that you have referenced and return results that make sense. Other functions will attempt to identify the relationship; however, for best results you should always create a relationship where possible. To learn more, see Formulas and the Tabular Model earlier in this article.  
  
## Updating the results of formulas (process)  

*Data process* and *recalculation* are two separate but related operations. You should thoroughly understand these concepts when designing a model that contains complex formulas, large amounts of data, or data that is obtained from external data sources.  
  
*Processing data* is the process of updating the data in a model with new data from an external data source.  
  
*Recalculation* is the process of updating the results of formulas to reflect any changes to the formulas themselves and to reflect changes in the underlying data. Recalculation can affect performance in the following ways:  
  
- The values in a calculated column are computed and stored in the model. To update the values in the calculated column, you must process the model using one of three processing commands - Process Full, Process Data, or Process Recalc. The result of the formula must always be recalculated for the entire column, whenever you change the formula.  
  
- The values calculated by measures are dynamically evaluated whenever a user adds the measure to a pivot table or open a report; as the user modifies the context, values returned by the measure change. The results of the measure always reflect the latest in the in-memory cache.  
  
Processing and recalculation have no effect on row filter formulas unless the result of a recalculation returns a different value, thus making the row queryable or not queryable by role members.  
  
## Troubleshooting errors in formulas  

If you get an error when defining a formula, the formula might contain either a *syntactic error*, *semantic error*, or *calculation error*.  
  
Syntactic errors are the easiest to resolve. They typically involve a missing parenthesis or comma. For help with the syntax of individual functions, see [DAX function reference](/dax/dax-function-reference).  
  
The other type of error occurs when the syntax is correct, but the value or the column referenced does not make sense in the context of the formula. Such semantic and calculation errors might be caused by any of the following problems:  
  
- The formula refers to a non-existing column, table, or function.  
  
- The formula appears to be correct, but when the data engine fetches the data it finds a type mismatch, and raises an error.  
  
- The formula passes an incorrect number or type of parameters to a function.  
  
- The formula refers to a different column that has an error, and therefore its values are invalid.  
  
- The formula refers to a column that has not been processed, meaning it has metadata but no actual data to use for calculations.  
  
In the first four cases, DAX flags the entire column that contains the invalid formula. In the last case, DAX grays out the column to indicate that the column is in an unprocessed state.  
  
## See also  

 [Data Analysis Expressions (DAX) Reference](/dax/data-analysis-expressions-dax-reference)  
 [Measures](../../analysis-services/tabular-models/measures-ssas-tabular.md)  
 [Calculated Columns](../../analysis-services/tabular-models/ssas-calculated-columns.md)  
 [Roles](../../analysis-services/tabular-models/roles-ssas-tabular.md)  
 [KPIs](../../analysis-services/tabular-models/kpis-ssas-tabular.md)  
 [Data Sources Supported](../../analysis-services/tabular-models/data-sources-supported-ssas-tabular.md)  
  
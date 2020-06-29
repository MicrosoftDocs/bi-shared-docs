---
title: "Specify Mark as Date Table in Analysis Services tabular models| Microsoft Docs"
ms.date: 04/03/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Specify Mark as Date Table for use with time intelligence

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

In order to use time intelligence functions in DAX formulas, you must specify a date table and a unique identifier (datetime) column of the Date data type. Once a column in the date table is specified as a unique identifier, you can create relationships between columns in the date table and any fact tables.  
  
When using time intelligence functions, the following rules apply:  
  
- When using DAX time intelligence functions, never specify a datetime column from a fact table. Always create a separate date table in your model with at least one datetime column of Date data type and with unique values.  
  
- Make sure your date table has a continuous date range.  
  
- The datetime column in the date table should be at day granularity (without fractions of a day).  
  
- You must specify a date table and a unique identifier column by using the **Mark the Date Table** dialog box.  
  
- Create relationships between fact tables and columns of Date data type in the date table.  
  
## Specify a date table and unique identifier
  
1. In Visual Studio, in the model designer, click the date table.  
  
1. Click **Extensions** > **Table** > **Date** > **Mark as Date Table**. 
  
1. In the **Mark as Date Table** dialog box, in the **Date** listbox, select a column to be used as a unique identifier. This column must contain unique values and should be of Date data type. For example:  
  
    a. |Date|  
    b. |----------|  
    c. |7/1/2010 12:00:00 AM|  
    d. |7/2/2010 12:00:00 AM|  
    e. |7/3/2010 12:00:00 AM|  
    f. |7/4/2010 12:00:00 AM|  
    g. |7/5/2010 12:00:00 AM|  
  
1. If necessary, create any relationships between fact tables and the date table.  
  
## See also  
  
 [Time intelligence Functions (DAX)](/dax/time-intelligence-functions-dax)  

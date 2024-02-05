﻿---
title: "Analysis Services tutorial lesson 6: Create measures | Microsoft Docs"
description: Learn how to create measures for an Analysis Services tabular model project.
ms.date: 02/20/2020
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: tutorial
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan
---
# Create measures

[!INCLUDE[appliesto-sql2019-later-aas-pbip](../includes/appliesto-sql2019-later-aas-pbip.md)]

In this lesson, you create measures to be included in your model. Similar to the calculated columns you created, a measure is a calculation created by using a DAX formula. However, unlike calculated columns, measures are evaluated based on a user selected *filter*. For example, a particular column or slicer added to the Row Labels field in a PivotTable. A value for each cell in the filter is then calculated by the applied measure. Measures are powerful, flexible calculations that you want to include in almost all tabular models to perform dynamic calculations on numerical data. To learn more, see [Measures](../tabular-models/measures-ssas-tabular.md).
  
To create measures, you use the *Measure Grid*. By default, each table has an empty measure grid; however, you typically do not create measures for every table. The measure grid appears below a table in the model designer when in Data View. To hide or show the measure grid for a table, click the **Table** menu, and then click **Show Measure Grid**.  
  
You can create a measure by clicking an empty cell in the measure grid, and then typing a DAX formula in the formula bar. When you click ENTER to complete the formula, the measure then appears in the cell. You can also create measures using a standard aggregation function by clicking a column, and then clicking the AutoSum button (**∑**) on the toolbar. Measures created using the AutoSum feature appear in the measure grid cell directly beneath the column, but can be moved.  
  
In this lesson, you create measures by both entering a DAX formula in the formula bar, and by using the AutoSum feature.  
  
Estimated time to complete this lesson: **30 minutes**  
  
## Prerequisites  

This article is part of a tabular modeling tutorial, which should be completed in order. Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 5: Create calculated columns](../tutorial-tabular-1400/as-lesson-5-create-calculated-columns.md).  
  
## Create measures  
  
#### To create a DaysCurrentQuarterToDate measure in the DimDate table  
  
1.  In the model designer, click the **DimDate** table.  
  
2.  In the measure grid, click the top-left empty cell.  
  
3.  In the formula bar, type the following formula:  
  
    ```
    DaysCurrentQuarterToDate:=COUNTROWS( DATESQTD( 'DimDate'[Date])) 
    ```
  
    Unlike calculated columns, with measure formulas you can type the measure name, followed by a colon, followed by the formula expression.

    Notice the top-left cell now contains a measure name, **DaysCurrentQuarterToDate**, followed by a result. The result is not relevant at this point because no user filter has been applied.
    
      ![Screenshot of the model designer with Days Current Quarter To Date: 92 called out.](../tutorial-tabular-1400/media/as-lesson6-newmeasure.png) 
    
    

  
#### To create a DaysInCurrentQuarter measure in the DimDate table  
  
1.  With the **DimDate** table still active in the model designer, in the measure grid, click the empty cell below the measure you created.  
  
2.  In the formula bar, type the following formula:  
  
    ```
    DaysInCurrentQuarter:=COUNTROWS( DATESBETWEEN( 'DimDate'[Date], STARTOFQUARTER( LASTDATE('DimDate'[Date])), ENDOFQUARTER('DimDate'[Date])))
    ```
  
    When creating a comparison ratio between one incomplete period and the previous period, the formula must calculate the proportion of the period that has elapsed and compare it to the same proportion in the previous period. In this case, [DaysCurrentQuarterToDate]/[DaysInCurrentQuarter] gives the proportion elapsed in the current period.  
  
#### To create an InternetDistinctCountSalesOrder measure in the FactInternetSales table  
  
1.  Click the **FactInternetSales** table.   
  
2.  Click the **SalesOrderNumber** column heading.  
  
3.  On the toolbar, click the down-arrow next to the AutoSum (**∑**) button, and then select **DistinctCount**.  
  
    The AutoSum feature automatically creates a measure for the selected column using the DistinctCount standard aggregation formula.  
    
       ![Screenshot of the model designer with Distinct Count Sales Order Number: 27659 called out.](../tutorial-tabular-1400/media/as-lesson6-newmeasure2.png)
  
4.  In the measure grid, click the new measure, and then in the **Properties** window, in **Measure Name**, rename the measure to **InternetDistinctCountSalesOrder**. 
 
  
#### To create additional measures in the FactInternetSales table  
  
1.  By using the AutoSum feature, create and name the following measures:  

    |Column|Measure name|AutoSum (∑)|Formula|  
    |----------------|----------|-----------------|-----------|  
    |SalesOrderLineNumber|InternetOrderLinesCount|Count|=COUNTA([SalesOrderLineNumber])|  
    |OrderQuantity|InternetTotalUnits|Sum|=SUM([OrderQuantity])|  
    |DiscountAmount|InternetTotalDiscountAmount|Sum|=SUM([DiscountAmount])|  
    |TotalProductCost|InternetTotalProductCost|Sum|=SUM([TotalProductCost])|  
    |SalesAmount|InternetTotalSales|Sum|=SUM([SalesAmount])|  
    |Margin|InternetTotalMargin|Sum|=SUM([Margin])|  
    |TaxAmt|InternetTotalTaxAmt|Sum|=SUM([TaxAmt])|  
    |Freight|InternetTotalFreight|Sum|=SUM([Freight])|  
  
2.  By clicking an empty cell in the measure grid, and by using the formula bar, create,  the following custom measures in order:  
  
      ```
      InternetPreviousQuarterMargin:=CALCULATE([InternetTotalMargin],PREVIOUSQUARTER('DimDate'[Date]))
      ```
      
      ```
      InternetCurrentQuarterMargin:=TOTALQTD([InternetTotalMargin],'DimDate'[Date])
      ```
  
      ```
      InternetPreviousQuarterMarginProportionToQTD:=[InternetPreviousQuarterMargin]*([DaysCurrentQuarterToDate]/[DaysInCurrentQuarter])
      ```
  
      ```
      InternetPreviousQuarterSales:=CALCULATE([InternetTotalSales],PREVIOUSQUARTER('DimDate'[Date]))
      ```
  
      ```
      InternetCurrentQuarterSales:=TOTALQTD([InternetTotalSales],'DimDate'[Date])
      ```
      
      ```
      InternetPreviousQuarterSalesProportionToQTD:=[InternetPreviousQuarterSales]*([DaysCurrentQuarterToDate]/[DaysInCurrentQuarter])
      ```
  
Measures created for the FactInternetSales table are used to analyze critical financial data such as sales, costs, and profit margin for items defined by the user selected filter.  

Now that you've created a bunch of measure, take a look at **Measures** in Tabular Model Explorer. You'll see all of your new measures. Right-click a measure and you see actions you can now take on a that measure.
  
## Next step

[Lesson 7: Create Key Performance Indicators](../tutorial-tabular-1400/as-lesson-7-create-key-performance-indicators.md)
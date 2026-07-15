---
title: "Create a New OLAP Mining Structure | Microsoft Docs"
description: Learn how to create an OLAP mining structure by using the Data Mining Wizard in Microsoft SQL Server Analysis Services.
ms.date: 10/31/2023
ms.service: azure-analysis-services
ms.custom: data-mining
ms.topic: how-to

---
# Create a new OLAP mining structure
[!INCLUDE[appliesto-sql2019-earlier](../includes/appliesto-sql2019-earlier.md)]

[!INCLUDE[dm-dep-banner](../includes/dm-dep-banner.md)]

  Use the Data Mining Wizard in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to create a mining structure that uses data from a multidimensional model. Mining models that are based on OLAP cubes can use the columns and values in fact tables, dimensions, and measure groups as attributes for analysis.
  
## To create a new OLAP mining structure  
  
1.  In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] Solution Explorer, right-click the **Mining Structures** folder in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then select **New Mining Structure** to open the Data Mining Wizard.  
  
1.  On the **Welcome to the Data Mining Wizard** page, select **Next**.  
  
1.  On **Select the Definition Method**, select **From existing cube** and then select **Next**.  
  
     If you get the error message **Unable to retrieve a list of supported data mining algorithms**, open the **Project Properties** dialog box and verify that you specified the name of an Analysis Services instance that supports multidimensional models. You can't create mining models on an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that supports tabular modeling.  
  
1.  On **Create the Data Mining Structure**, decide whether to create a mining structure only, or a mining structure plus one related mining model. It's usually easier to create a mining model at the same time, so you're prompted to include necessary columns.  
  
     If you choose to create a mining model, select the data mining algorithm that you want to use and then select **Next**. For more information about how to choose an algorithm, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](../../analysis-services/data-mining/data-mining-algorithms-analysis-services-data-mining.md).  
  
1.  On **Select the Source Cube Dimension**, under **Select a Source Cube Dimension**, locate the dimension that contains the majority of your case data, and then select **Next**.  
  
     For example, if you're trying to identify customer groupings, you might choose the Customer dimension. If you're trying to analyze purchases across transactions, you might choose the Internet Sales Order Details dimension. You're not restricted to using only the data in this dimension, but the dimension should contain important attributes to use in analysis.  
  
1.  On **Select the Case Key**, under **Attributes**, select the attribute to be the key of the mining structure, and then select **Next**.  
  
     Typically, the attribute that you use as key for the mining structure is also a key for the dimension and is preselected.  
  
1.  On **Select Case Level Columns**, under **Related Attributes and Measures**, select the attributes and measures that contain values you want to add to the mining structure as case data. Select **Next**.  
  
1.  On **Specify Mining Model Column Usage**, under **Mining model structure**, first set the predictable column, and then choose columns to use as inputs.  
  
    -   Select a check box in the left column to include the data in the mining structure. You can include columns in the structure to use for reference but not for analysis. You can't use columns you designate as keys for input or prediction.  
  
    -   Select the check box in the **Input** column to use the attribute as a variable in analysis.  
  
    -   Select the check box in the **Predict** column only for predictable attributes.  
  
1. Select **Next**.  
  
1. On **Specify Mining Model Column Usage**, you can also use **Add Nested Tables** and **Nested Tables** to add and remove nested tables in the mining structure.  
  
     In an OLAP mining model, a nested table is another data set within the cube that has a one-to-many relationship with the dimension representing the case attributes. Therefore, when the dialog box opens, it preselects measure groups that are already related to the dimension you selected as the case table. At this point, you can choose a different dimension that contains additional information useful for analysis.  
  
     For example, if you're analyzing customers, you use the [Customer] dimension as the case table. For the nested table, you might add the reason customers gave for making a purchase, which is included in the [Sales Reason] dimension.  
  
     If you add nested data, you must specify two more columns:  
  
    -   The key of the nested table: This key is preselected on the **Select Nested Table Key** page.  
  
    -   The attributes or attributes to use for analysis: The **Select Nested Table Columns** page provides a list of measures and attributes in the nested table selection.  
  
        -   For each attribute that you include in the model, check the box in the left column.  
  
        -   If you want to use the attribute for analysis only, check **Input**.  
  
        -   If you want to include the column as one of the predictable attributes for the model, select **Predict**.  
  
        -   Any item that you include in the structure but don't specify as an input or predictable attribute is added to the structure with the **Ignore** flag. This flag means that the data is processed when you build the model but isn't used in analysis, and is available only for drillthrough. This flag can be handy for including details such as customer names that you don't want to use in analysis.  
  
     Select **Finish** to close the nested table section of the wizard. You can repeat the preceding process to add multiple nested columns.  
  
1. On **Specify Columns' Content and Data Type**, under **Mining model structure**, set the content type and data type for each column, and then select **Next**.  
  
    > [!NOTE]  
    >  OLAP mining models don't support using the **Detect** feature to automatically detect whether a column contains continuous or discrete data.  
  
1. On **Slice Source Cube**, you can filter the data that is used to create the mining structure.  
  
     Slice the cube to restrict the data used to build the model. For example, you could build separate models for each region by slicing on the [Geography] hierarchy and on: 
  
    -   **Dimension**: A related dimension from the dropdown list.  
  
    -   **Hierarchy**:  The level of the dimension hierarchy at which to apply the filter. For example, if you're slicing by the [Geography] dimension, choose a hierarchy level such as country/region name.  
  
    -   **Operator**: An operator from the list.  
  
    -   **Filter Expression**: A value or expression to serve as the filter condition. You can  use the dropdown list to select a value from the list of members at the specified level of the hierarchy.  
  
         For example, if you select [Geography] as the dimension and country/region name as the hierarchy level, the dropdown list contains all the valid countries or regions that you can use as a filter condition. You can make multiple selections. The data in the mining structure is then limited to cube data from these geographical areas.  
  
     Ignore the **Parameters** check box. This dialog box supports multiple cube filtering scenarios, but this option isn't relevant to building a mining structure.  
  
1. Select **Next**.  
  
1. On **Split data into training and testing sets**, specify a percentage of the mining structure data to reserve for testing, or specify the maximum number of test cases. If you specify both values, the limits are combined to use whichever is lowest. Select **Next**.  
  
1. On **Completing the Wizard**, provide a name for the new OLAP mining structure and the initial mining model, and then select **Finish**.  
  
1. On **Completing the Wizard**, you can also create a mining model dimension and/or a cube by using the mining model dimension. These options are supported only for models built by using the following algorithms:  
  
    -   Microsoft Clustering algorithm  
  
    -   Microsoft Decision Trees algorithm  
  
    -   Microsoft Association Rules algorithm  
  
     To create a new dimension, select the **Create mining model dimension** check box and provide a type name for the dimension. When you use this option, you create a new dimension within the original cube used to build the mining structure. Use this dimension to drill down and conduct further analysis. Because the dimension is located within the cube, the dimension is automatically mapped to the case data dimension.  
  
     To create a new cube, select the **Create cube using mining model dimension** check box and provide a name for the new cube. When you use this option, you create a new cube that contains both the existing dimensions used in building the structure and the new dimension that contains the results from the model.
  
## See also
 [Mining Structure Tasks and How-tos](../../analysis-services/data-mining/mining-structure-tasks-and-how-tos.md)  
  
  

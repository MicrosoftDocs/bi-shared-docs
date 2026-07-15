---
title: "Create an OLAP Mining Structure | Microsoft Docs"
description: Learn how to create an OLAP mining structure based on a dimension and related measures in an existing multidimensional solution.
ms.date: 10/31/2023
ms.service: azure-analysis-services
ms.custom: data-mining
ms.topic: how-to

---
# Create an OLAP mining structure
[!INCLUDE[appliesto-sql2019-earlier](../includes/appliesto-sql2019-earlier.md)]

[!INCLUDE[dm-dep-banner](../includes/dm-dep-banner.md)]

  Creating a data mining model based on an OLAP cube or other multidimensional data store has many advantages. An OLAP solution already contains large amounts of well organized, cleaned, and properly formatted data. However, the complexity of the data makes it difficult to find meaningful patterns through ad hoc exploration. Data mining provides the ability to discover new correlations and actionable insights.  
  
 This article describes how to create an OLAP mining structure based on a dimension and related measures in an existing multidimensional solution.  
  
##  <a name="bkmk_Reqs"></a> Requirements for OLAP mining structure and models  
 When you design an OLAP mining model, the data source already exists in the database used to build the cube. You can't connect to a remote cube and build data mining objects. You must have the cube objects and database available within the same solution as the mining structure you build.  
  
 If you don't have the original project files or don't want to alter them, you can use the **Import from Server (Multidimensional or Data Mining)** option in Visual Studio to get a copy of the metadata and solution objects. You can then modify the deployment target, edit data sources, and work with the cube objects without affecting the existing objects.  
  
 For more information, see [Import a Data Mining Project using the Analysis Services Import Wizard](../../analysis-services/data-mining/import-a-data-mining-project-using-the-analysis-services-import-wizard.md).  
  
##  <a name="bkmk_Overview"></a> Overview of the OLAP data mining process  
 Start the Data Mining Wizard by right-clicking the **Mining Structures** node in Solution Explorer and selecting  **New Mining Structure**. The wizard guides you through the following steps to create the structure for a new structure and model:  
  
1.  **Select the Definition Method**: Select a data source type and choose **From existing cube**.  
  
    > [!NOTE]  
    >  The OLAP cube that you use as a source must exist within the same database as the mining structure. Also, you can't use a cube created by the [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] for Excel add-in as a source for data mining.  
  
1.  **Create the Data Mining Structure**: Determine whether to build just a structure, or a structure with a mining model.  
  
     You must also choose an appropriate algorithm for analyzing your data. For guidance on which algorithm is best for certain tasks, see  [Data Mining Algorithms (Analysis Services - Data Mining)](ms-help://SQL111033/as_1devconc/html/ed1fc83b-b98c-437e-bf53-4ff001b92d64.htm).  
  
1.  **Select the Source Cube Dimension**: This step is the same as selecting a data source. Choose the single dimension that contains the most important data used for training your model. You can add data from other dimensions or filter the dimension later.  
  
1.  **Select the Case Key**: Within the dimension that you just selected, choose an attribute column to serve as the unique identifier for your case data.  
  
     Typically a column is preselected, but you can change the column if there are multiple keys.  
  
1.  **Selecting Case Level Columns**: Choose the attributes and related measures from the selected dimension that are relevant to your analysis. This step is equivalent to selecting columns from a table.  
  
     The wizard automatically includes any measures created using attributes from the selected dimension for your review and selection.  
  
     For example, if your cube contains a measure that calculates freight cost based on the customer's geographical location, and you chose the Customer dimension as your main data source for modeling, the measure is proposed as a candidate for adding to the model. Avoid adding too many measures that are already directly based on attributes. There's already one implicit relationship between the columns, as defined in the measure formula, and the strength of this expected correlation can obscure other relationships you might otherwise discover.  
  
1.  **Specify Mining Model Column Usage**: For each attribute or measure that you added to the structure, you must specify whether the attribute should be used for prediction or as input. If you don't select either of these options, the data is processed but not used for analysis. The data is available as background data in case you enable drillthrough later.  
  
1.  **Add nested tables**: Select this option to add related tables.
 
   1.  In the **Select a Measure Group Dimension** dialog box, choose a single dimension from the dimensions that are related to the current dimension.  
  
   1. Use the **Select a Nested Table Key** dialog box to define how the new dimension is related to the dimension that contains the case data.  
  
   1. Use the **Select Nested Table Columns** dialog box to choose the attributes and measures from the new dimension that you want to use in analysis. Also specify whether the nested attribute is used for prediction.  
  
   1. After you add all the nested attributes you need, return to the **Specify Mining Model Column Usage** page and select **Next**.  
  
1.  **Specify Columns Content and Data Type**: After you add all the data to use for analysis, specify the *data type* and *content type* for each attribute.  
  
     In an OLAP model, you don't have the option to automatically detect data types, because the data type is already defined by the multidimensional solution and can't be changed. Keys are also automatically identified. For more information, see  [Data Types (Data Mining)](../../analysis-services/data-mining/data-types-data-mining.md).  
  
     The *content type* that you choose for each column that you use in the model tells the algorithm how the data should be processed. For more information, see [Content Types (Data Mining)](../../analysis-services/data-mining/content-types-data-mining.md).  
  
1. **Slicing the source cube**: Define filters in a cube to select just a subset of data to train models that are more targeted.  
  
     Filter a cube by choosing the dimension to filter on, selecting the level of the hierarchy that contains the criteria you want to use, and then entering a condition to use as the filter.  
  
1. **Create Testing Set**: Select how much data should be set aside to use in testing the model. If your data supports multiple models, it's a good idea to create a holdout data set so that all models can be tested on the same data.  
  
     For more information, see [Testing and Validation (Data Mining)](../../analysis-services/data-mining/testing-and-validation-data-mining.md).  
  
1. **Completing the Wizard**: Give a name to the new mining structure and the associated mining model, and save the structure and model.  
  
     On this page, you can also set the following options:  
  
    -   **Allow drillthrough**  
  
    -   **Create mining model dimension**  
  
    -   **Create cube using mining model dimension**  
  
     To learn more about these options, see [Understanding Data Mining Dimensions and Drillthrough](#bkmk_DMDimension) later in this article.  
  
At this point, the mining structure and its model are just metadata. You need to process both to get results.
  
##  <a name="bkmk_OLAP_Scenarios"></a> Scenarios for using data mining with OLAP data  
 OLAP cubes often contain so many members and dimensions that it's difficult to know where to begin with data mining. To help identify the patterns that the cubes contain, you can identify a single dimension of interest and begin to explore patterns related to that dimension. The following table lists several common OLAP data mining tasks, describes sample scenarios for applying each task, and identifies the data mining algorithm to use for each task.  
  
|Task|Sample scenario|Algorithm|  
|----------|---------------------|---------------|  
|Group members into clusters|Segment a customer dimension based on customer member properties, the products that the customers buy, and the amount of money that the customers spend.|[!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering Algorithm|  
|Find interesting or abnormal members|Identify interesting or abnormal stores in a store dimension based on sales, profit, store location, and store size.|[!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees Algorithm|  
|Find interesting or abnormal cells|Identify store sales that go against typical trends over time.|[!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series Algorithm|  
|Find correlations|Identify factors that are related to server downtime, including region, machine type, OS, or purchase date.|[!INCLUDE[msCoName](../includes/msconame-md.md)] Naïve Bayes algorithm|  
  
##  <a name="bkmk_Filters"></a> Slicing a cube versus filtering models  
 Slicing the cube while you're building a model is like creating a filter on a relational mining model. In a relational model, the filter on the data source is defined as a WHERE clause on a SQL statement. In a cube, you use the editor to create filter statements by using MDX.  
  
 For example, a cube might contain information about purchases of products worldwide, but for your marketing campaign, you want to create a model based on analysis of female customers over 30 who live in the United Kingdom. In this scenario, you create two filters:  
  
-   For the first filter, choose the **Geography** dimension, choose the hierarchy for **Region**, and then use the **Filter Expression** list to choose **United Kingdom** from the possible values.  
  
-   For the second filter, choose the **Customer** dimension, select the **Gender** attribute, and select **Female** from the list of attribute values.  
  
 After you create the mining structure, you can modify both the definition of the cube data and the filter criteria. For more information, see [Filters for Mining Models](~/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).  
  
 Both the **Mining Structure** tab and the **Mining Model** tab provide an option to add a filter to an existing mining structure by selecting **Define a Cube Slice**. The **Slice Cube** dialog box helps you build a valid MDX filter expression by choosing values from dropdown lists.  
  
> [!IMPORTANT]  
>  The interface for designing and browsing cubes changed in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]. For more information, see [Browse data and metadata in Cube](../../analysis-services/multidimensional-models/browse-data-and-metadata-in-cube.md).  
  
 You can add as many filters on the cube as are required to return the data that you need for the mining model. You can also define slices on individual cube slices. For example, if your structure contains two nested tables that are based on products, you could slice one table on March 2004 and the other table on April 2004. The resulting model could then be used to predict purchases made in April based on the purchases that were made in March.  
  
##  <a name="bkmk_Nested"></a> Using nested tables in an OLAP mining model  
 When you use the Data Mining Wizard to build a model based on cube data, you can add nested tables by specifying the names of related dimensions and then choosing the attributes or measures to add to the model.  
  
 For example, if the main dimension used for case data is Customer, you might add as a related dimension the Products dimension, because you expect that a customer might order multiple products over time, and the cube already links each customer to the many products via the order fact tables.  
  
 You add nested tables in the **Specify Mining Model Column Usage** page of the wizard by selecting **Add Nested Tables**. A dialog box opens that guides you through the process of choosing a related dimension and any measures. The case and nested dimensions must be related by a foreign key, and measures must use one of the attributes that are already included in the case or nested tables. These restrictions don't narrow the scope much, so you must be careful to select only those attributes that are useful for modeling.  
  
 For each attribute or measure that you add to the nested table, you must specify whether the nested attribute is used for prediction by selecting **Predictable** or **Input** in the **Select Nested Table Columns** dialog box. If you don't select either of these options, the data is added to the mining structure but not used for analysis.  
  
 For each attribute and measure, you must also specify whether the attribute is discrete, discretized, or continuous. The wizard preselects a default based on the data type of the attribute, but you might need to change these values depending on the algorithm requirements. If you choose a content type that isn't compatible with the algorithm you choose, for example you use a continuous numeric type with a Naïve Bayes model, you get an error message when you try to process the model.  
  
 When you finish setting these options, the wizard adds the nested table to the case table. The default name for the nested table is the nested dimension name, but you can rename the nested table and its columns. You can repeat this process to add multiple nested tables to the mining structure.  
  
 The ability to use nested table data is a feature of SQL Server data mining that is particularly powerful, and there are almost limitless possibilities for using related subsets of data in a cube.  
  
##  <a name="bkmk_DMDimension"></a> Understanding data mining dimensions and drillthrough  

 The **Allow drillthrough** option lets you run queries against the underlying cube data while you browse the model. The data isn't contained in the new data mining dimension, but the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database can use the data bindings to retrieve the information from the source cube.  
  
 The **Create mining model dimension** option lets you generate a new dimension within the existing cube that contains the patterns discovered by the algorithm. The hierarchy within the new dimension is determined largely by the model type. For example, the representation of a clustering model is fairly flat, with the (All) node at the top of the hierarchy and each cluster in the next level. In contrast, the dimension that is created for a decision tree model might have a very deep hierarchy, representing the branching of the tree.  
  
 The **Create cube using mining model dimension** option lets you export the new data mining dimension into a new cube. Any objects required for drillthrough on the data mining dimension are included automatically.  
  
> [!IMPORTANT]  
>  Only model types based on the Microsoft Clustering algorithm, the Microsoft Decision Trees algorithm, or the Microsoft Association algorithm support the creation of data mining dimensions.  
  
## See also
 [Data Mining Algorithms (Analysis Services - Data Mining)](../../analysis-services/data-mining/data-mining-algorithms-analysis-services-data-mining.md)  
 [Mining Structure Columns](../../analysis-services/data-mining/mining-structure-columns.md)   
 [Mining Model Columns](../../analysis-services/data-mining/mining-model-columns.md)   
 [Mining Model Properties](../../analysis-services/data-mining/mining-model-properties.md)   
 [Properties for Mining Structure and Structure Columns](../../analysis-services/data-mining/properties-for-mining-structure-and-structure-columns.md)  
  
  

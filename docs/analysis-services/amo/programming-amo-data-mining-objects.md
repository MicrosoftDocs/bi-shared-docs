---
title: "Programming AMO Data Mining objects | Microsoft Docs"
description: In this article, learn how to program data mining objects by using Analysis Management Objects (AMO).
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: amo
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan
monikerRange: "asallproducts-allversions || sql-analysis-services-2016 || sql-analysis-services-2017 || sql-analysis-services-2019"
---
# Programming AMO Data Mining objects

[!INCLUDE[appliesto-sqlas-aas](../includes/appliesto-sqlas-aas.md)]

  Programming data mining objects by using AMO is simple and straightforward. The first step is to create the data structure model to support the mining project. Then you create the data mining model that supports the mining algorithm you want to use in order to predict or to find the unseen relationships underlying your data. With your mining project created (including structure and algorithms), you can then process the mining models to obtain the trained models that you will use later when querying and predicting from the client application.  
  
 One thing to remember is that AMO is not for querying; AMO is for managing and administering your mining structures and models. To query your data, use [Developing with ADOMD.NET](../adomd/developing-with-adomd-net.md).  
  
## MiningStructure objects

 A mining structure is the definition of the data structure that is used to create all mining models. A mining structure contains a binding to a data source view that is defined in the database, and contains definitions for all columns participating in the mining models. A mining structure can have more than one mining model.  
  
 Creating a <xref:Microsoft.AnalysisServices.MiningStructure> object requires the following steps:  
  
1. Create the <xref:Microsoft.AnalysisServices.MiningStructure> object and populate the basic attributes. Basic attributes include object name, object ID (internal identification), and data source binding.  
  
2. Create columns for the model. Columns can be either scalar or table definitions.  
  
     Each column needs a name and internal ID, a type, a content definition, and a binding.  
  
3. Update the <xref:Microsoft.AnalysisServices.MiningStructure> object to the server, by using the Update method of the object.  
  
     Mining structures can be processed, and when they are processed, the children mining models are processed or retrained.  
  
 The following sample code creates a mining structure to forecast sales in a time series. Before running the sample code, make sure that the database *db*, passed as parameter for `CreateSalesForecastingMiningStructure`, contains in `db.DataSourceViews[0]` a reference to the view *dbo.vTimeSeries* in the Adventure Works Data Warehouse sample database.  
  
```csharp  
public static MiningStructure CreateSalesForecastingMiningStructure(Database db)  
{  
    MiningStructure ms = db.MiningStructures.FindByName("Forecasting Sales Structure");  
    if (ms != null)  
        ms.Drop();  
    ms = db.MiningStructures.Add("Forecasting Sales Structure", "Forecasting Sales Structure");  
    ms.Source = new DataSourceViewBinding(db.DataSourceViews[0].ID);  
  
    ScalarMiningStructureColumn amount = ms.Columns.Add("Amount", "Amount");  
    amount.Type = MiningStructureColumnTypes.Double;  
    amount.Content = MiningStructureColumnContents.Continuous;  
    amount.KeyColumns.Add("vTimeSeries", "Amount", OleDbType.Currency);  
  
    ScalarMiningStructureColumn modelRegion = ms.Columns.Add("Model Region", "Model Region");  
    modelRegion.IsKey = true;  
    modelRegion.Type = MiningStructureColumnTypes.Text;  
    modelRegion.Content = MiningStructureColumnContents.Key;  
    modelRegion.KeyColumns.Add("vTimeSeries", "ModelRegion", OleDbType.WChar, 56);  
  
    ScalarMiningStructureColumn qty = ms.Columns.Add("Quantity", "Quantity");  
    qty.Type = MiningStructureColumnTypes.Long;  
    qty.Content = MiningStructureColumnContents.Continuous;  
    qty.KeyColumns.Add("vTimeSeries", "Quantity", OleDbType.Integer);  
  
    ScalarMiningStructureColumn timeIndex = ms.Columns.Add("TimeIndex", "TimeIndex");  
    timeIndex.IsKey = true;  
    timeIndex.Type = MiningStructureColumnTypes.Long;  
    timeIndex.Content = MiningStructureColumnContents.KeyTime;  
    timeIndex.KeyColumns.Add("vTimeSeries", "TimeIndex", OleDbType.Integer);  
  
    ms.Update();  
    return ms;  
}  
```  
  
## MiningModel objects

 A mining model is a repository for all columns and column definitions that will be used in a mining algorithm.  
  
 Creating a <xref:Microsoft.AnalysisServices.MiningModel> object requires the following steps:  
  
1. Create the <xref:Microsoft.AnalysisServices.MiningModel> object and populate the basic attributes.  
  
     Basic attributes include object name, object ID (internal identification), and mining algorithm specification.  
  
2. Add the columns of the mining model. One of the columns must be defined as the case key.  
  
3. Update the <xref:Microsoft.AnalysisServices.MiningModel> object to the server, by using the Update method of the object.  
  
     <xref:Microsoft.AnalysisServices.MiningModel> objects can be processed independently of other models in the parent <xref:Microsoft.AnalysisServices.MiningStructure>.  
  
 The following sample code creates a Microsoft Time Series forecasting model based on the "Forecasting Sales Structure" mining structure:  
  
```csharp  
public static MiningModel CreateSalesForecastingMiningModel(MiningStructure ms)  
{  
    if (ms.MiningModels.ContainsName("Sales Forecasting Model"))  
    {  
        ms.MiningModels["Sales Forecasting Model"].Drop();  
    }  
    MiningModel mm = ms.CreateMiningModel(true, "Sales Forecasting Model");  
    mm.Algorithm = MiningModelAlgorithms.MicrosoftTimeSeries;  
    mm.AlgorithmParameters.Add("PERIODICITY_HINT", "{12}");  
  
    MiningModelColumn amount = new MiningModelColumn();  
    amount.SourceColumnID = "Amount";  
    amount.Usage = MiningModelColumnUsages.Predict;  
  
    MiningModelColumn modelRegion = new MiningModelColumn();  
    modelRegion.SourceColumnID = "Model Region";  
    modelRegion.Usage = MiningModelColumnUsages.Key;  
  
    MiningModelColumn qty = new MiningModelColumn();  
    qty.SourceColumnID = "Quantity";  
    qty.Usage = MiningModelColumnUsages.Predict;  
  
    MiningModelColumn ti = new MiningModelColumn();  
    ti.SourceColumnID = "TimeIndex";  
    ti.Usage = MiningModelColumnUsages.Key;  
  
    mm.Update();  
    mm.Process(ProcessType.ProcessFull);  
    return mm;  
}  
```

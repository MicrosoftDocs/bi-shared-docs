---
title: "Analysis Services DAX properties | Microsoft Docs"
description: Learn about the DAX section of msmdsrv.ini which contains settings used to control certain query behaviors in Analysis Services.
ms.date: 05/03/2021
ms.prod: sql
ms.technology: analysis-services
ms.custom: 
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || >= sql-analysis-services-2016"
---
# DAX properties

[!INCLUDE[ssas-appliesto-sqlas-all-aas](../includes/ssas-appliesto-sqlas-all-aas.md)]

For SQL Server Analysis Services, the DAX section of msmdsrv.ini contains settings used to control certain query behaviors in Analysis Services, such as the upper limit on the number of rows returned in a DAX query result set. For Azure Analysis Services, this property can be specified by using XMLA.

For very large rowsets, such as those returned in DirectQuery models, the default of one million rows could be insufficient. You'll know whether the limit needs adjusting if you get this error: "The result set of a query to external data source has exceeded the maximum allowed size of '1000000' rows."

To increase the upper limit, specify the **MaxIntermediateRowSize** configuration setting. You will need to manually add the entire element to the DAX section of the configuration file. The setting is not present in the file until you add it.

## Configuration snippet (msmdsrv.ini)

```
<ConfigurationSettings>
. . .
<DAX>
  <PredicateCheckSpoolCardinalityThreshold>5000
  </PredicateCheckSpoolCardinalityThreshold>
  <DQ>
     <MaxIntermediateRowsetSize>1000000
     </MaxIntermediateRowsetSize>
  </DQ>
</DAX>
. . .
```

## Property descriptions

Setting |Value |Description
--------|-------|-----------
MaxIntermediateRowsetSize | 1000000 | Maximum number of rows returned in a DAX query. For SSAS, manually add this entry to the msmdsrv.ini file and increase the value if the default is too low.
PredicateCheckSpoolCardinalityThreshold| 5000 | An advanced property that you should not change, except under the guidance of Microsoft support.

For more information about additional server properties and how to set them, see [Server properties in Analysis Services](../../analysis-services/server-properties/server-properties-in-analysis-services.md).

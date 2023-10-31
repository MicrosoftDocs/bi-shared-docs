---
title: "Measure Element (CSDLBI) | Microsoft Docs"
description: Learn about the Measure element, a complex type based on the CSDL Property element that supports business intelligence data models.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Measure Element (CSDLBI)

[!INCLUDE[csdl-archived](../includes/csdl-archived.md)]

  The Measure element is a complex type based on the CSDL Property element. The CSDLBI annotations add attributes that support definition of complex formulas for use in business intelligence data models.  
  
## Elements and Attributes  
 The following table lists the elements and attributes that define the Measure element, in addition to all attributes applicable to the Property element.  
  
|Name|Is Required|Description|  
|----------|-----------------|-----------------|  
|Kpi|No|Required element only for measures that are used as KPIs. Not all measures are KPIs, but all KPIs must be based on the definition of a measure.<br /><br /> [KPI Element &#40;CSDLBI&#41;](kpi-element-csdlbi.md)|  
|IsSimpleMeasure|No|A true/false value that indicates whether the formula used in the measure is one of the simple aggregations (SUM, COUNT, MIN, MAX, AVG, DistinctCount).<br /><br /> The default is true.|  
  
## Example Tabular 
  
 The following sample, in CSDLBI version 1.1, shows two measures from the AdventureWorks tabular model sample. The second measure has been converted to a KPI, by adding KPI elements.  
  
```xml   
  
<Property   
    Name="Order_Lines_Count"   
    Type="Int64">  
<bi:Measure   
    Caption="Order Lines Count"   
    ReferenceName="Order Lines Count"   
    Width="0"   
    IsSimpleMeasure="false" />  
</Property>  
  
<Property   
    Name="Total_Current_Quarter_Sales_Performance"   
    Type="Double">  
<bi:Measure   
    Caption="Total Current Quarter Sales Performance"   
    ReferenceName="Total Current Quarter Sales Performance"   
    Width="0"   
    IsSimpleMeasure="false">  
    <bi:Kpi   
    StatusGraphic="Three Signs Colored">  
      <bi:KpiGoal>  
        <bi:PropertyRef Name="Measures___Total_Current_Quarter_Sales_Performance_Goal_" />  
      </bi:KpiGoal>  
      <bi:KpiStatus>  
        <bi:PropertyRef Name="Measures___Total_Current_Quarter_Sales_Performance_Status_" />  
      </bi:KpiStatus>  
    </bi:Kpi>  
  </bi:Measure>  
</Property>  
```  
  
## Example Multidimensional 
  
 The following sample, in CSDLBI version 1.1, shows a measure from the Contoso Operations cube that is being used as a KPI.  
  
```xml   
  
<Property   
    Name="Sum_of_SalesAmount"   
    Type="Decimal" Precision="19" Scale="4">  
<Documentation>  
<Summary>KPI Description</Summary>  
</Documentation>  
<bi:Measure   
    Caption="Sum of SalesAmount"   
    ReferenceName="Sum of SalesAmount"   
    FormatString="\$#,0.00;(\$#,0.00);\$#,0.00">  
<bi:Kpi   
    StatusGraphic="Three Circles Colored">  
    <bi:KpiGoal>  
        <bi:PropertyRef Name="v_Sum_of_SalesAmount_Goal" />  
    </bi:KpiGoal>  
    <bi:KpiStatus>  
        <bi:PropertyRef Name="v_Sum_of_SalesAmount_Status" />  
    </bi:KpiStatus>  
</bi:Kpi>  
</bi:Measure>  
</Property>  
```  

  

---
title: "KPI Element (CSDLBI) | Microsoft Docs"
description: Learn about the Kpi element, which defines a calculation that can be used as a Key Performance Indicator in a business intelligence data model.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# KPI Element (CSDLBI)

[!INCLUDE[csdl-archived](../includes/csdl-archived.md)]

  The Kpi element defines a calculation that can be used as a Key Performance Indicator (KPI). In a business intelligence data model, KPIs are based on measures, and as such the definition of the KPI contains all the metadata associated with measures, as well as information needed for presentation of the KPI values, including a default graphic.  
  
 The Kpi element does not specify the formula, which is contained in the measure definition, but rather specifies the additional metadata that is associated with measures that are used as KPIs. Once you have designated a measure as a KPI, you cannot use it as a measure in other contexts.  
  
## Elements and Attributes  
 The following table lists the elements and attributes that define the Kpi element.  
  
|Name|Is Required|Description|  
|----------|-----------------|-----------------|  
|Documentation|No|A description of the KPI.|  
|KpiGoal|Yes|A reference to a column containing values that can be used as the goal.<br /><br /> See [PropertyRef Element &#40;CSDLBI&#41;](propertyref-element-csdlbi.md).|  
|KpiStatus|Yes|A reference to a column containing values that represent the current status of the KPI.|  
|StatusGraphic|Yes|A reference to an image that indicates negative, neutral, or positive progress against the targets defined in the KPI.|  
  
## Remarks  
 When you design a model, you can create a KPI by creating a measure and then assigning the measure to use as a KPI. You then add information that is specific to KPIs, such as a graphic to use in showing trends.  
  
## Example Tabular  
  
 The following sample, in CSDLBI version 1.0, shows a KPI that measures sales, from the AdventureWorks tabular model sample.  
  
```xml   
  
<Property Name="InternetCurrSalesPerf" Type="Double">  
  <bi:Measure>  
    <bi:Kpi StatusGraphic="Three Stars Colored">  
      <bi:KpiGoal>  
        <bi:PropertyRef Name="v_InternetCurrSalesPerf_Goal" />  
      </bi:KpiGoal>  
      <bi:KpiStatus>  
        <bi:PropertyRef Name="v_InternetCurrSalesPerf_Status" />  
      </bi:KpiStatus>  
    </bi:Kpi>  
  </bi:Measure>  
</Property>  
  
```  
  
## Example Multidimensional  
  
 The following sample, in CSDLBI version 1.1, shows a KPI from the Contoso Operations cube.  
  
```xml   
<Property Name="Sum_of_SalesAmount" Type="Decimal" Precision="19" Scale="4">  
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
  

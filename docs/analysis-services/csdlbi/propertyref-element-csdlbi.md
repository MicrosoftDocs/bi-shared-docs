---
title: "PropertyRef Element (CSDLBI) | Microsoft Docs"
description: Learn about the PropertyRef element, a simple type that provides a reference to a column that supplies a value required by another property.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# PropertyRef Element (CSDLBI)

[!INCLUDE[csdl-archived](../includes/csdl-archived.md)]

  The PropertyRef element is a simple type that provides a reference to a column that supplies a value required by another property.  
  
## Elements and Attributes  
 The following table lists the elements and attributes that define the PropertyRef element.  
  
|Name|Is Required|Description|  
|----------|-----------------|-----------------|  
|Name|Yes|A string containing the name of the property that is the target of the reference.|  
  
## PropertyRefs Element  
 PropertyRefs is a complex type that defines a collection of properties, with each property contained in a PropertyRef element.  
  
 The following table lists the elements and attributes of the PropertyRefs type.  
  
|Name|Is Required|Description|  
|----------|-----------------|-----------------|  
|PropertyRef|Yes|A string containing the property reference.|  
  
## Example Tabular 
  
 The following sample, in CSDLBI version 1.1, shows a PropertyRef element that specifies the source of a formula that is used in a measure, from the AdventureWorks tabular model sample.  
  
```xml   
<bi:Measure Caption="Total Current Quarter Margin Performance" ReferenceName="Total Current Quarter Margin Performance" Width="0" IsSimpleMeasure="false">  
  <bi:Kpi StatusGraphic="Three Symbols UnCircled Colored">  
    <bi:KpiGoal>  
      <bi:PropertyRef Name="Measures___Total_Current_Quarter_Margin_Performance_Goal_" />  
    </bi:KpiGoal>  
    <bi:KpiStatus>  
      <bi:PropertyRef Name="Measures___Total_Current_Quarter_Margin_Performance_Status_" />  
    </bi:KpiStatus>  
  </bi:Kpi>  
</bi:Measure>  
```  
  
## Example Multidimensional
  
 The following sample, in CSDLBI version 1.1, shows a KPI from the Contoso Operations cube. The PropertyRef elements point to the columns that contains the formula or values that are used to define the KPI's goal and status relative to that goal.  
  
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
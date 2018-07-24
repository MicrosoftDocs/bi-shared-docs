---
title: "Batch Element (XMLA) | Microsoft Docs"
ms.date: 07/24/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Batch Element (XMLA)

  Performs one or more XML for Analysis (XMLA) commands as a batch operation, either sequentially or in parallel, on an instance of Analysis Services.  
  
## Syntax  
  
```xml  
  
<Command>  
   <Batch Transaction="Boolean" ProcessAffectedObjects="Boolean">  
      <Bindings>...</Bindings>  
      <DataSource>...</DataSource>  
      <DataSourceView>...</DataSourceView>  
      <ErrorConfiguration>...</ErrorConfiguration>  
      <Parallel>...</Parallel>  
      <!-- One or more XMLA commands -->  
   </Batch>  
</Command>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Command](../xml-elements-properties/command-element-xmla.md)|  
|Child elements|[Bindings](../xml-elements-properties/bindings-element-xmla.md), [DataSource](../xml-elements-properties/datasource-element-xmla.md), [DataSourceView](../xml-elements-properties/datasourceview-element-xmla.md), [ErrorConfiguration](../../../analysis-services/scripting/objects/errorconfiguration-element-assl.md), [Parallel](../xml-elements-properties/parallel-element-xmla.md)<br /><br /> One or more of the following XMLA commands: [Alter](../xml-elements-commands/alter-element-xmla.md), [Backup](../xml-elements-commands/backup-element-xmla.md), [BeginTransaction](../xml-elements-commands/begintransaction-element-xmla.md), [ClearCache](../xml-elements-commands/clearcache-element-xmla.md), [CommitTransaction](../xml-elements-commands/committransaction-element-xmla.md), [Create](../xml-elements-commands/create-element-xmla.md), [Delete](../xml-elements-commands/delete-element-xmla.md), [DesignAggregations](../xml-elements-commands/designaggregations-element-xmla.md), [Drop](../xml-elements-commands/drop-element-xmla.md), [Insert](../xml-elements-commands/insert-element-xmla.md), [Lock](../xml-elements-commands/lock-element-xmla.md), [MergePartitions](../xml-elements-commands/mergepartitions-element-xmla.md), [NotifyTableChange](../xml-elements-commands/notifytablechange-element-xmla.md), [Process](../xml-elements-commands/process-element-xmla.md), [Restore](../xml-elements-commands/restore-element-xmla.md), [RollbackTransaction](../xml-elements-commands/rollbacktransaction-element-xmla.md), [SetPasswordEncryptionKey](http://msdn.microsoft.com/fb262737-f0f4-4441-985e-3b2a94d00a9e), [Statement](../xml-elements-commands/statement-element-xmla.md), [Subscribe](../xml-elements-commands/subscribe-element-xmla.md), [Synchronize](../xml-elements-commands/synchronize-element-xmla.md), [Unlock](../xml-elements-commands/unlock-element-xmla.md), [Update](../xml-elements-commands/update-element-xmla.md), [UpdateCells](../xml-elements-commands/drop-element-xmla.md)|  
  
## Attributes  
  
|Attribute|Description|  
|---------------|-----------------|  
|ProcessAffectedObjects|(Optional **Boolean** attribute) Indicates whether all objects that require reprocessing will be processed.<br /><br /> If set to true, the Analysis Services instance processes any objects that require reprocessing as a result of processing an object included in the **Batch** command.<br /><br /> If set to **false**, the Analysis Services instance processes only those objects included in the **Batch** command.|  
|Transaction|(Optional **Boolean** attribute) Indicates whether the command included in the **Batch** command are treated as a single transaction or individual transactions.<br /><br /> If set to true, all of the commands included in the **Batch** command are considered a single transaction. If any command fails, the commands executed prior to the failed command are rolled back, and the **Batch** command stops without executing subsequent commands.<br /><br /> If set to **false**, the **Batch** command attempts to execute every command, and commits the results of each command that completes successfully.|  
  
## Remarks  
  
> [!WARNING]  
>  Command/Execute/Statement is currently not supported in a Batch operation.  

---
title: "Detach Element | Microsoft Docs"
description: Learn how the Detach element detaches a Analysis Services database from the current server instance.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference

---
# Detach Element

  Detaches a Analysis Services database from the current server instance.  
  
## Syntax  
  
```xml  
  
<Command>  
   <Detach>  
      <Object>...</Object>  
      <Password>...</Password>  
   </Detach>  
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
|Child elements|[Object](../xml-elements-properties/object-element-xmla.md)<br /><br /> [Password](../xml-elements-properties/password-element-xmla.md)|  
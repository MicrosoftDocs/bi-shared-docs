---
title: "MDX Scripting Fundamentals (Analysis Services) | Microsoft Docs"
description: Learn MDX scripting fundamentals like how changing an MDX script associated with a cube immediately changes the calculation process for the cube.
ms.date: 05/02/2018
ms.service: analysis-services
ms.custom: mdx
ms.topic: conceptual

---
# MDX Scripting Fundamentals (Analysis Services)
[!INCLUDE[appliesto-sqlas](../../includes/appliesto-sqlas.md)]
  In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], a Multidimensional Expressions (MDX) script is made up of one or more MDX expressions or statements that populate a cube with calculations.  
  
 An MDX script defines the calculation process for a cube. An MDX script is also considered part of the cube itself. Therefore, changing an MDX script associated with a cube immediately changes the calculation process for the cube.  
  
 To create MDX scripts, you can use Cube Designer in the [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]. For more information, see [Define Assignments and Other Script Commands](../../../analysis-services/multidimensional-models/define-assignments-and-other-script-commands.md) and [Introduction to MDX Scripting in Microsoft SQL Server 2005](/previous-versions/sql/sql-server-2005/administrator/ms345116(v=sql.90)).  
  
 For performance issues related to MDX queries and calculations, see the MDX optimization section in the [SQL Server Analysis Services Performance Guide](/previous-versions/dn749781(v=msdn.10)).  
  
## In This Section  
  
|Topic|Description|  
|-----------|-----------------|  
|[The Basic MDX Script &#40;MDX&#41;](../../../analysis-services/multidimensional-models/mdx/the-basic-mdx-script-mdx.md)|Details the basic MDX script, including the default MDX script provided in each cube, and how MDX scripts generally function within a cube in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].|  
|[Managing Scope and Context &#40;MDX&#41;](../../../analysis-services/multidimensional-models/mdx/managing-scope-and-context-mdx.md)|Describes how to use the [CALCULATE](/sql/mdx/mdx-scripting-calculate) statement, the [SCOPE](/sql/mdx/mdx-scripting-scope) statement, and the [This](/sql/mdx/this-mdx) function to manage context and scope within an MDX script.|  
|[Using Variables and Parameters &#40;MDX&#41;](../../../analysis-services/multidimensional-models/mdx/using-variables-and-parameters-mdx.md)|Describes how to use variables and parameters in an MDX script.|  
|[Error Handling &#40;MDX&#41;](../../../analysis-services/multidimensional-models/mdx/error-handling-mdx.md)|Explains error handling within an MDX script.|  
|[Supported MDX &#40;MDX&#41;](../../../analysis-services/multidimensional-models/mdx/supported-mdx-mdx.md)|Provides a list of supported MDX operators, statements, and functions within an MDX script.|  
  
## See Also  
 [MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx)  
  

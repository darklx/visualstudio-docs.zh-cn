---
title: "表达式评估接口 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: expression evaluation, interfaces
ms.assetid: 2d259f60-2cd7-460e-b02d-24a8fb202850
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c6a9d1d63b4fb15a920f175013af8a05cb38beb8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="expression-evaluation-interfaces"></a>表达式评估接口
> [!IMPORTANT]
>  在 Visual Studio 2015 中，已弃用这种方式实施表达式计算器。 有关实现 CLR 表达式计算器的信息，请参阅[CLR 表达式计算器](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)和[托管表达式计算器示例](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)。  
  
 以下是表达式评估接口[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]Debugging SDK。  
  
## <a name="discussion"></a>讨论  
 这些接口用于评估在中断模式下的调用堆栈中的表达式。 它们仅对公共语言运行时表达式计算器 (EE) 被实现。  
  
 表中的每个接口显示可以从以下列表中实现它的组件：  
  
-   调试引擎 (DE)  
  
-   表达式计算器 (EE)  
  
-   Visual Studio (VS)  
  
|接口|由实现|描述|  
|---------------|--------------------|-----------------|  
|[IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)|EE|表示变量的数值别名。|  
|[IDebugAlias2](../../../extensibility/debugger/reference/idebugalias2.md)|EE|表示的数字别名的变量，并可将表达式计算器 (EE) 以获取该别名的应用程序域。|  
|[IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)|EE|表示一个数组对象。|  
|[IDebugArrayObject2](../../../extensibility/debugger/reference/idebugarrayobject2.md)|EE|表示一个托管的数组对象，并允许的表达式计算器 (EE) 来确定数组的基索引 （下限）。|  
|[IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)|DE|表示绑定调试到内存中的实际地址的符号联编程序。|  
|[IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)|DE|与相同[IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)接口但提供对类型、 别名和自定义可视化工具的访问权限。|  
|[IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)|EE|表示表达式计算器。|  
|[IDebugExpressionEvaluator2](../../../extensibility/debugger/reference/idebugexpressionevaluator2.md)|EE|表示的表达式计算器 (EE) 的增强的版本。|  
|[IDebugExpressionEvaluator3](../../../extensibility/debugger/reference/idebugexpressionevaluator3.md)|EE|增强型的分析器目录树表示的表达式计算器 (EE)。|  
|[IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)|EE|表示一个函数。|  
|[IDebugFunctionObject2](../../../extensibility/debugger/reference/idebugfunctionobject2.md)|EE|表示一个函数，并增强[IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)接口。|  
|[IDebugIDECallback](../../../extensibility/debugger/reference/idebugidecallback.md)|DE|使表达式计算器 (EE) 在调试器的输出窗口中显示一条消息。|  
|[IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)|EE|表示托管的代码的对象。|  
|[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)|EE|表示任何符号的基接口绑定到的内存地址。|  
|[IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)|EE|与相同[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)接口但提供的其他信息的访问。|  
|[IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)|EE|分析的表达式准备要进行求值表示。|  
|[IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)|EE|表示的指针。|  
|[IDebugPointerObject3](../../../extensibility/debugger/reference/idebugpointerobject3.md)|EE|表示在分析树中，指向并扩展**IDebugPointerObject**接口。|  
|[IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)|EE|提供的功能，以修改通过类型可视化工具的类型的值。|  
|[IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)|VS|提供对自定义查看器和类型可视化工具的访问。|  
|[IEEVisualizerServiceProvider](../../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)|VS|提供的功能创建[IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)对象。|  
|[IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md)|EE|表示一套[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)对象。|  
  
## <a name="see-also"></a>另请参阅  
 [API 参考](../../../extensibility/debugger/reference/api-reference-visual-studio-debugging.md)   
 [编写 CLR 表达式计算器](../../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [类型可视化工具和自定义查看器](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)
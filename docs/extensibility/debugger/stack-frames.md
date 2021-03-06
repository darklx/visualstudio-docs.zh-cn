---
title: "堆栈帧 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- stack frames, debugging
- debugging [Debugging SDK], stack frames
- stack frames
ms.assetid: b5e439d4-1e9d-4e13-9cad-bb8b136d4ca8
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a2b225d84bfae6d182da86b2878a3761f67572be
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="stack-frames"></a>堆栈帧
在调试器体系结构，方面**堆栈帧**:  
  
-   是抽象中提供一个线程的执行上下文。 在函数中始终执行线程。 堆栈帧保存到它的函数和参数的本地变量。 若要使用 Visual Studio 进行调试，语言或正在调试的环境必须支持堆栈帧。  
  
-   可以了标识和描述自身，以及可以返回相关联的线程。 表示当前指令指针，以及关联的文档的代码上下文和表达式计算上下文，还可以返回一个堆栈帧。  
  
-   具有名称、 类型和值的本地变量和自变量，用于描述和在各种 IDE 调试窗口中显示的属性。  
  
-   由[IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md)接口，通常创建的调试引擎 (DE) 或虚拟机，因此执行线程。  
  
## <a name="see-also"></a>另请参阅  
 [调试器上下文](../../extensibility/debugger/debugger-contexts.md)   
 [调试器概念](../../extensibility/debugger/debugger-concepts.md)   
 [调试引擎](../../extensibility/debugger/debug-engine.md)   
 [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md)
---
title: "调试本机代码 |Microsoft 文档"
ms.custom: 
ms.date: 04/11/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging native code
- debugging [C++], native code
- debugging [Visual Studio], native code
- native code, debugging
ms.assetid: d94eee90-7e0d-4cac-88c1-9831030daa5e
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3ee0ec7e8314008550267c40bb4811c90783777c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="debugging-native-code"></a>调试本机代码
本节讲述本机应用程序的一些常见调试问题和调试技术。 本节阐述的技术属于高级别技术。 有关使用 Visual Studio 调试器的机制，请参阅[调试器路线图](../debugger/debugger-basics.md)。  
  
## <a name="in-this-section"></a>本节内容  
 [如何：调试优化的代码](../debugger/how-to-debug-optimized-code.md)  
 给出有关调试优化代码的提示，具体地，包括应调试未优化版本的程序的理由，“Debug”和“Release”配置的默认优化设置，以及有关如何查找仅出现在优化代码中的 bug 的提示（在“Debug”版本配置中打开优化）。  
  
 [DebugBreak 和 __debugbreak](../debugger/debugbreak-and-debugbreak.md)  
 描述 Win32 `DebugBreak` 函数，并提供指向其位于 Platform SDK 中的参考主题的链接。 还描述了 `__debugbreak` 内部。  
  
 [C/C++ 断言](../debugger/c-cpp-assertions.md)  
 讨论断言语句，包括它们的工作方式，使用它们的好处（捕捉逻辑错误、检查操作的结果和测试错误情况），它们与 `_DEBUG` 的交互，以及 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 中受支持的断言类型。  
  
 [如何：调试内联程序集代码](../debugger/how-to-debug-inline-assembly-code.md)  
 提供有关使用“反汇编”窗口查看程序集指令和使用“寄存器”窗口查看寄存器内容的简短说明，并提供指向关于这些窗口的主题的链接。  
  
 [MFC 调试技术](../debugger/mfc-debugging-techniques.md)  
 将您链接到 MFC 程序的调试技术，包括：afxDebugBreak、TRACE 宏、在 MFC 中检测内存泄漏、MFC 断言以及降低 MFC 调试版本的大小。  
  
 [CRT 调试方法](../debugger/crt-debugging-techniques.md)  
 链接到用于 C 运行库的调试技术，包括：使用 CRT 调试库、用于报告的宏、malloc 和 _malloc_dbg 之间的差异、编写调试挂钩函数以及 CRT 调试堆。  
  
 [调试本机代码常见问题解答](../debugger/debugging-native-code-faqs.md)  
 提供有关调试 Visual C++ 程序的常见问题的答案  
  
 [调试 COM 和 ActiveX](../debugger/com-and-activex-debugging.md)  
 提供有关调试 COM 和 ActiveX 应用程序的信息，包括用于 COM 和 ActiveX 调试的工具。  
  
 [如何：调试插入的代码](../debugger/how-to-debug-injected-code.md)  
 提供有关如何调试使用特性的代码的指导。 指导信息包括如何打开“源批注”、如何查看插入的代码以及如何在当前执行点查看反汇编代码。  
  
 [演练：调试并行应用程序](../debugger/walkthrough-debugging-a-parallel-application.md)  
 介绍如何使用**并行任务**和**并行堆栈**工具窗口调试并行应用程序。  
  
## <a name="related-sections"></a>相关章节  
 [Visual C++ 项目类型](../debugger/debugging-preparation-visual-cpp-project-types.md)  
 提供指向特定主题的链接，这些主题描述如何调试由 Visual C++ 项目模板创建的本机项目类型。  

 [调试 DLL 项目](../debugger/debugging-dll-projects.md)提供有关如何调试本机和托管 Dll 的信息。
  
 [调试器功能简介](../debugger/debugger-feature-tour.md)  
 提供指向调试文档的较大章节的链接。 涉及的信息包括：调试器的新增功能、设置和准备、断点、处理异常、编辑和继续、调试托管代码、调试本机代码、调试 SQL 以及用户界面参考。  
  
## <a name="see-also"></a>另请参阅  
 [调试器安全](../debugger/debugger-security.md)  
 [在 Visual Studio 中调试](../debugger/index.md)[调试器功能教程](../debugger/debugger-feature-tour.md)
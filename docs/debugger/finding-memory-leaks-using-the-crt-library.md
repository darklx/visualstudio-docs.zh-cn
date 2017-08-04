---
title: "使用 CRT 库查找内存泄漏 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "_crtBreakAlloc"
  - "_CRTDBG_MAP_ALLOC"
  - "_CrtDumpMemoryLeaks"
  - "_CrtMemCheckpoint"
  - "_CrtMemDifference"
  - "_CrtMemDumpStatistics"
  - "_CrtMemState"
  - "_CrtSetBreakAlloc"
  - "_CrtSetDbgFlag"
  - "_CrtSetReportMode"
  - "断点, 内存分配"
  - "调试内存泄漏"
  - "内存泄漏"
  - "内存泄漏, 检测和隔离"
  - "内存, 调试"
ms.assetid: cf6dc7a6-cd12-4283-b1b6-ea53915f7ed1
caps.latest.revision: 28
caps.handback.revision: 28
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 使用 CRT 库查找内存泄漏
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

内存泄漏，即未能正确释放以前分配的内存，是 C\/C\+\+ 应用程序中最难以捉摸也最难以检测到的 Bug 之一。 最初少量内存泄漏可能不引人注目，但随着时间的推移，内存泄漏越来越多，就会出现一些征兆，包括性能下降，在应用程序内存不足时发生崩溃。 更严重的是，占用了所有可用内存的泄漏应用程序可能会导致其他应用程序崩溃，从而无法确定问题出在哪个应用程序。 即使看似无害的内存泄漏也可能说明存在其他问题应当纠正。  
  
 借助 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 调试器和 C 运行时 \(CRT\) 库，可以检测和识别内存泄漏。  
  
## 启用内存泄漏检测  
 检测内存泄漏的主要工具是调试器和 C 运行库 \(CRT\) 调试堆函数。  
  
 若要启用调试堆函数，请在程序中包括以下语句：  
  
```  
#define _CRTDBG_MAP_ALLOC #include <stdlib.h> #include <crtdbg.h>  
```  
  
 为了 CRT 函数能够正常工作，`#include` 语句必须遵循此处所示的顺序。  
  
 包含 crtdbg.h，将 `malloc` 和 [free](/visual-cpp/c-runtime-library/reference/free) 函数映射到它们的调试版本，即 [\_malloc\_dbg](/visual-cpp/c-runtime-library/reference/malloc-dbg) 和 `free`，它们将跟踪内存分配和释放。 此映射只在包含 `_DEBUG` 的调试版本中发生。 发布版本使用普通的 `malloc` 和 `free` 函数。  
  
 `#define` 语句将 CRT 堆函数的基础版本映射到对应的调试版本。 如果省略 `#define` 语句，内存泄漏转储将有所简化。  
  
 使用这些语句启用调试堆函数之后，可以在某个应用程序退出点之前设置一个对 `_CrtDumpMemoryLeaks` 的调用，以便在应用程序退出时显示内存泄漏报告：  
  
```  
_CrtDumpMemoryLeaks();  
```  
  
 如果应用程序有多个退出点，并不需要在每个退出点都手动设置一个对 [\_CrtDumpMemoryLeaks](/visual-cpp/c-runtime-library/reference/crtdumpmemoryleaks) 的调用。 应用程序开头部分对 `_CrtSetDbgFlag` 的调用会导致在每个退出点自动调用 `_CrtDumpMemoryLeaks`。 你必须设置两个位域，如下所示：  
  
```  
_CrtSetDbgFlag ( _CRTDBG_ALLOC_MEM_DF | _CRTDBG_LEAK_CHECK_DF );  
```  
  
 默认情况下，`_CrtDumpMemoryLeaks` 将内存泄漏报告输出到“输出”窗口的“调试”窗格中。 你可以使用 `_CrtSetReportMode` 将该报告重定向到其他位置。  
  
 如果使用库，该库可能会将输出重置到另一位置。 在此情况下，可以将输出位置设置回“输出”窗口，如下所示：  
  
```  
_CrtSetReportMode( _CRT_ERROR, _CRTDBG_MODE_DEBUG );  
```  
  
## 解释内存泄漏报告  
 如果应用程序未定义 `_CRTDBG_MAP_ALLOC`，则 [\_CrtDumpMemoryLeaks](/visual-cpp/c-runtime-library/reference/crtdumpmemoryleaks) 显示的内存泄漏报告如下所示：  
  
```  
Detected memory leaks! Dumping objects -> {18} normal block at 0x00780E80, 64 bytes long. Data: <                > CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD Object dump complete.  
```  
  
 如果应用程序定义了 `_CRTDBG_MAP_ALLOC`，则显示的内存泄漏报告如下所示：  
  
```  
Detected memory leaks! Dumping objects -> C:\PROGRAM FILES\VISUAL STUDIO\MyProjects\leaktest\leaktest.cpp(20) : {18} normal block at 0x00780E80, 64 bytes long. Data: <                > CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD Object dump complete.  
```  
  
 区别在于，第二份报告显示文件名，以及泄漏的内存初次分配所在位置的行号。  
  
 不论是否定义 `_CRTDBG_MAP_ALLOC`，内存泄漏报告都显示以下信息：  
  
-   内存分配编号，在本例中为 `18`  
  
-   [块类型](http://msdn.microsoft.com/zh-cn/e2f42faf-0687-49e7-aa1f-916038354f97)，在本例中为 `normal`。  
  
-   十六进制内存位置，在本例中为 `0x00780E80`。  
  
-   块的大小，在本例中为 `64 bytes`。  
  
-   块中前 16 个字节的数据（十六进制形式）。  
  
 内存泄漏报告将内存块标识为普通、客户端或 CRT。“普通块”是由程序分配的普通内存。“客户端块”是由 MFC 程序用于需要析构函数的对象的特殊类型内存块。 MFC `new` 运算符根据正在创建的对象的需要创建普通块或客户端块。“CRT 块”是由 CRT 库为自己使用而分配的内存块。 CRT 库可处理这些块的释放。 因此，你不大可能在内存泄漏报告中看到这些块，除非出现严重错误（例如 CRT 库损坏）。  
  
 内存泄漏报告中绝对不会出现另外两个内存块类型。“可用块”是已释放的内存。 也就是说，根据定义，这种块不会泄漏。“忽略块”是已明确标记、不出现在内存泄漏报告中的块。  
  
 这些方法适用于使用标准 CRT `malloc` 函数分配的内存。 不过，如果程序使用 C\+\+ `new` 运算符分配内存，则需要重新定义 `new` 才能在内存泄漏报告中看到文件和行号。 你可以利用如下所示的代码块实现：  
  
```  
#ifdef _DEBUG #ifndef DBG_NEW #define DBG_NEW new ( _NORMAL_BLOCK , __FILE__ , __LINE__ ) #define new DBG_NEW #endif #endif  // _DEBUG  
```  
  
## 在内存分配编号上设置断点  
 如果分配了泄漏内存块，内存分配编号会通知你。 例如，内存分配编号为 18 的块就是在应用程序运行过程中所分配的第 18 个内存块。 CRT 报告包含运行过程中的所有内存块分配情况。 其中包括 CRT 库和其他库（如 MFC）的分配情况。 因此，内存分配编号为 18 的块可能不是你的代码所分配的第 18 个内存块。 通常，二者并不一致。  
  
 可以使用分配编号在内存分配位置设置断点。  
  
#### 使用“监视”窗口设置内存分配断点  
  
1.  在应用程序的起点附近设置断点，然后启动应用程序。  
  
2.  当应用程序在断点处中断时，会出现“监视”窗口。  
  
3.  在“监视”窗口中，在“名称”列中键入 `_crtBreakAlloc`。  
  
     如果要使用 CRT 库的多线程 DLL 版本（\/MD 选项），请加入上下文运算符：`{,,ucrtbased.dll}_crtBreakAlloc`  
  
4.  按“Return”。  
  
     调试器将计算调用，并将结果放入“值”列。 如果没有在内存分配上设置任何断点，该值将为 –1。  
  
5.  在“值”列中，将显示的值替换为要在其位置中断的内存分配的分配编号。  
  
 在某个内存分配编号设置断点之后，你可以继续调试。 请注意在与以前运行相同的条件下运行程序，以便内存分配顺序不会更改。 当程序在指定的内存分配处中断时，可以使用“调用堆栈”窗口和其他调试器窗口来确定分配内存时的情况。 然后，可以继续执行程序以观察对象发生什么情况，并确定未正确释放对象的原因。  
  
 在对象上设置数据断点可能也有帮助。 有关详细信息，请参阅 [使用断点](../debugger/using-breakpoints.md)。  
  
 你也可以在代码中设置内存分配断点。 有两种方法可以实现此目的：  
  
```  
_crtBreakAlloc = 18;  
```  
  
 或：  
  
```  
_CrtSetBreakAlloc(18);  
```  
  
## 比较内存状态  
 定位内存泄漏的另一种技术涉及在关键点对应用程序的内存状态拍快照。 若要为应用程序中给定点的内存状态拍快照，请创建 **\_CrtMemState** 结构，将它传递给 `_CrtMemCheckpoint` 函数。 该函数用当前内存状态的快照填充此结构：  
  
```  
_CrtMemState s1; _CrtMemCheckpoint( &s1 );  
  
```  
  
 `_CrtMemCheckpoint` 会将当前内存状态填充在该结构中。  
  
 若要输出 **\_CrtMemState** 结构的内容，请将该结构传递给 `_ CrtMemDumpStatistics` 函数：  
  
```  
_CrtMemDumpStatistics( &s1 );  
  
```  
  
 `_ CrtMemDumpStatistics` 输出内存状态转储，如下所示：  
  
```  
0 bytes in 0 Free Blocks. 0 bytes in 0 Normal Blocks. 3071 bytes in 16 CRT Blocks. 0 bytes in 0 Ignore Blocks. 0 bytes in 0 Client Blocks. Largest number used: 3071 bytes. Total allocations: 3764 bytes.  
  
```  
  
 若要确定在某个代码部分中是否发生了内存泄漏，可以对这部分之前和之后的内存状态拍快照，然后使用 `_ CrtMemDifference` 比较两个状态：  
  
```  
_CrtMemCheckpoint( &s1 ); // memory allocations take place here _CrtMemCheckpoint( &s2 ); if ( _CrtMemDifference( &s3, &s1, &s2) ) _CrtMemDumpStatistics( &s3 );  
```  
  
 `_CrtMemDifference` 比较内存状态 `s1` 和 `s2`，在 \(`s3`\) 中返回结果，即 `s1` 与 `s2` 的差异。  
  
 寻找内存泄漏的一个方法是，首先在应用程序的开头和结尾部分放置 `_CrtMemCheckpoint` 调用，然后使用 `_CrtMemDifference` 比较两个结果。 如果 `_CrtMemDifference` 显示有内存泄漏，你可以添加更多 `_CrtMemCheckpoint` 调用来使用二进制搜索划分程序，直至找到泄漏源。  
  
## 误报  
 在某些情况下，`_CrtDumpMemoryLeaks` 可能给出错误的内存泄漏指示。 如果使用将内部分配标记为 \_NORMAL\_BLOCK 而不是 `_CRT_BLOCK` 或 `_CLIENT_BLOCK` 的库，则可能发生这种情况。 在这种情况下，`_CrtDumpMemoryLeaks` 无法区分用户分配和内部库分配。 如果在 `_CrtDumpMemoryLeaks` 调用点之后运行库分配的全局析构函数，则每个内部库分配都会报告为内存泄漏。 在 Visual Studio .NET 之前的早期版本的标准模板库会导致 `_CrtDumpMemoryLeaks` 出现这种误报，在最近的版本中，已经解决了这一问题。  
  
## 请参阅  
 [CRT 调试堆详细信息](../debugger/crt-debug-heap-details.md)   
 [调试器安全](../debugger/debugger-security.md)   
 [调试本机代码](../debugger/debugging-native-code.md)
---
title: "查看使用 IntelliTrace 事件 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1c9c91a-0009-4c4e-9b4f-c9ab3a6022a7
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eff33b87d647d28f4af8f452ea4662656a15a61e
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="view-events-with-intellitrace-in-visual-studio"></a>在 Visual Studio 中使用 IntelliTrace 查看事件
你可以使用 IntelliTrace 来收集关于特定事件或事件类别的信息，或收集关于除了事件外的单个函数调用的信息。 下列过程演示如何执行此操作。  
  
 你可以在 Visual Studio Enterprise 版，但不可在 Professional 或 Community 版中使用 IntelliTrace。  
  
##  <a name="GettingStarted"></a>配置 Intellitrace  
 你可以尝试仅使用 IntelliTrace 事件进行调试。 IntelliTrace 事件是调试器事件、异常、.NET Framework 事件和其他系统事件。 你应在开始调试之前打开或关闭特定事件以控制 IntelliTrace 记录的事件。 有关详细信息，请参阅[IntelliTrace 功能](../debugger/intellitrace-features.md)。  
  
 - 打开 IntelliTrace 事件以进行文件访问。 转到**工具 > 选项 > IntelliTrace > IntelliTrace 事件**页，然后展开**文件**类别。 检查 **“文件”** 事件类别。 这将导致检查所有文件事件（访问、关闭、删除）。

## <a name="create-your-app"></a>创建你的应用程序
  
1.  创建 C# 控制台应用程序。 在 Program.cs 文件中，添加以下 `using` 语句：  
  
    ```CSharp  
    using System.IO;  
    ```  
  
2.  在 Main 方法中，创建 <xref:System.IO.FileStream> ，从其中进行读取、将其关闭，然后删除该文件。 添加另一行，添加该行的唯一目的是留出设置断点的位置：  
  
    ```CSharp  
    static void Main(string[] args)  
    {  
        FileStream fs = File.Create("WordSearchInputs.txt");  
        fs.ReadByte();  
        fs.Close();  
        File.Delete("WordSearchInputs.txt");  
  
        Console.WriteLine("done");  
    }  
    ```  
  
3.  在 `Console.WriteLine("done");`上设置断点  

## <a name="start-debugging-and-view-intellitrace-events"></a>启动调试以及查看 IntelliTrace 事件
  
1.  照常启动调试。 (按**F5**或单击**调试 > 启动调试**。  
  
    > [!TIP]
    >  保留**局部变量**和**自动**调试以查看并记录这些窗口中的值时，窗口将打开。  
  
2.  执行在断点处停止。 如果看不到**诊断工具**窗口中，单击**调试 > Windows > IntelliTrace 事件**。  
  
     在 **“诊断工具”** 窗口中，找到 **“事件”** 选项卡（应该看到 **“事件”**、 **“内存使用”**和 **“CPU ”**三个选项卡）。 **“事件”** 选项卡显示按时间排序的事件列表，以调试器中断执行之前的最后一个事件结尾。 你应会看到一个名为 **“访问 WordSearchInputs.txt”**的事件。  
  
     以下屏幕截图取自 Visual Studio 2015 Update 1。  
  
     ![IntelliTrace &#45;Update1](../debugger/media/intellitrace-update1.png "IntelliTrace Update1")  
  
3.  选择该事件以展开其详细信息。  
  
     以下屏幕截图取自 Visual Studio 2015 Update 1。  
  
     ![IntelliTraceUpdate1 &#45;SingleEvent](../debugger/media/intellitraceupdate1-singleevent.png "IntelliTraceUpdate1 SingleEvent")  
  
     你可以选择路径名链接以打开文件。 如果完整的路径名不可用，则将显示 **“打开文件”** 对话框。  
  
     单击**激活历史调试**，这将调试器的上下文设置为所选的事件的时间收集、 显示历史数据**调用堆栈**，**局部变量**和其他参与的调试器窗口。 如果源代码可用，则 Visual Studio 会将指针移到源窗口中的相应代码，以便你可以检查它。  
  
     以下屏幕截图取自 Visual Studio 2015 Update 1。  
  
     ![HistoricalDebugging &#45;Update1](../debugger/media/historicaldebugging-update1.png "HistoricalDebugging Update1")  
  
4.  如果找不到 bug，请尝试检查导致 bug 的其他事件。 还可以让 IntelliTrace 记录调用信息，以便你可以单步执行函数调用。 
  
## <a name="next-steps"></a>后续步骤

你可以使用的一些高级功能的 IntelliTrace 历史调试：

 - 若要查看快照，请参阅[查看使用 IntelliTrace 步骤后的快照](../debugger/how-to-use-intellitrace-step-back.md)
 - 若要了解如何检查变量和浏览代码，请参阅[检查你的应用使用历史调试](../debugger/historical-debugging-inspect-app.md)
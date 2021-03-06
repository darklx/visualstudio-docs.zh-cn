---
title: "常规选项卡上，线程属性对话框中 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [Visual Studio], thread properties
- thread properties
ms.assetid: 46b6c668-6786-456e-97dc-337bcac0d812
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a2af344735b88fb7091ec438638c948a7f7f2ca4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="general-tab-thread-properties-dialog-box"></a>“线程属性”对话框 ->“常规”选项卡
使用此对话框中，若要了解有关特定线程的详细信息。 若要显示此对话框中，将焦点移至[线程视图](../debugger/threads-view.md)窗口中或打开[消息视图](../debugger/messages-view.md)展开一条消息。 在树中，选择任何线程节点，然后选择**属性**从**视图**菜单。  
  
 **线程属性**对话框中包含一个窗格中，**常规**选项卡。以下设置将可用：  
  
|条目|描述|  
|-----------|-----------------|  
|**模块名**|模块的名称。|  
|**线程 ID**|此线程的唯一 ID。 请注意，会重复使用线程 ID 号;它们仅针对该线程的生存期内标识一个线程。|  
|**进程 ID**|此进程的唯一 ID。 进程 ID 号会重复使用，以便它们仅针对该进程的生存期的标识过程。 运行程序时创建的进程对象类型。 在进程中的所有线程共享相同的地址空间，并有权访问相同的数据。 选择此值可查看的属性的进程 id。|  
|**线程状态**|线程的当前状态。 运行的线程使用处理器;备用线程是为使用其中一个。 就绪线程正在等待使用处理器，因为其中一个不是免费。 转换中的线程正在等待的资源，若要执行，例如等待其执行堆栈以便从磁盘中分页。 正在等待的线程不需要处理器，因为它正在等待外围操作完成或等待资源变得可用。|  
|**等待原因**|只有当线程处于等待状态时，这是适用。 事件对用于与受保护的子系统进行通信。|  
|**CPU 时间**|在此过程，并且其线程上花费的总 CPU 时间。 用户的时间 + Privileged 的 Time 等于。|  
|**用户的时间**|此线程已花费在用户模式下执行代码的总运行时间。 窗口管理器和图形引擎等类子系统一样，应用程序以用户模式下执行。|  
|**Privileged 的 Time**|此线程在特权模式下的执行代码所用总运行时间。 当调用 Windows 系统服务时，服务通常会在特权模式下，若要获取对系统专有数据的访问权限。 此类数据不会发生访问由在用户模式中执行的线程。 对系统的调用可能显式，或者它们可能是隐式的如页错误或中断发生时。|  
|**运行时间**|此线程已运行的总运行时间 （以秒为单位）。|  
|**当前优先级**|此线程的当前动态优先级。 进程中的线程可以引发和降低其自己的基本优先级相对于进程的基本优先级。|  
|**基本优先级**|此线程当前基本优先级。|  
|**起始地址**|启动此线程的虚拟地址。|  
|**用户的 PC**|线程用户程序计数器。|  
|**上下文切换**|从一个线程切换到另一个数。 线程交换机可在单个进程内或跨进程。 通过询问有关信息，另一个线程或被抢占时更高优先级的线程已准备好运行的线程，则可能会导致线程切换。|
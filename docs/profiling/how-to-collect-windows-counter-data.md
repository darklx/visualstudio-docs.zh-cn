---
title: "如何：收集 Windows 计数器数据 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.property.syscounter
- vs.performance.property.wincounter
helpviewer_keywords:
- windows counters
- performance tools, using windows counters
- profiling tools, using windows counters
ms.assetid: db4fbac2-bea5-4558-aa8b-160fcccf4b33
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d5b16cf6260932f11c9d4fd33f2eb5662327355a
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2017
---
# <a name="how-to-collect-windows-counter-data"></a>如何：收集 Windows 计数器数据
Windows 计数器是在分析期间可按设定的时间间隔收集的系统性能计数器。 在“分析工具”报表的“标记”视图中，针对每个收集间隔，行被标记为“自动标记”。 该行包含描述该间隔内的性能计数器值的列。 若要将分析限制在两个特定标记之间的时间段内，请选择这些标记，右键单击，并从快捷菜单中选择“筛选依据” ->  “标记”。  
  
 **要求**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
> [!NOTE]
>  Windows 8 和 Windows Server 2012 中增强的安全功能需要以 Visual Studio 探查器在这些平台上收集数据的方式进行重大更改。 UWP 应用也需要新的收集技术。 请参阅 [Windows 8 和 Windows Server 2012 应用程序上的性能工具](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)。  
  
### <a name="to-collect-windows-counter-data"></a>收集 Windows 计数器数据  
  
1.  在“性能资源管理器”中，右键单击想要配置其 Windows 计数器的会话，然后选择“属性”。  
  
2.  在“属性页”中，单击“Windows 计数器”。  
  
3.  选择“收集 Windows 计数器”复选框。  
  
4.  在“收集间隔(毫秒)”文本框中，键入一个时间间隔。  
  
5.  从“计数器类别”下拉列表中选择一个类别。  
  
6.  从“实例”下拉列表中选择一个实例。  
  
7.  选择分析应用程序时要使用的计数器。  
  
8.  单击“应用”。  
  
## <a name="see-also"></a>另请参阅  
 [配置性能会话](../profiling/configuring-performance-sessions.md)   
 [性能会话属性](../profiling/performance-session-properties.md)   
 [CPU 和 Windows 计数器](../profiling/cpu-and-windows-counters.md)
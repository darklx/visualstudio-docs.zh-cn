---
title: "语句不声明“AddHandler”、“RemoveHandler”或“RaiseEvent”方法 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31113"
  - "bc31113"
helpviewer_keywords: 
  - "BC31113"
ms.assetid: f8299c9d-6030-43e5-878e-8d2b042191b5
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 语句不声明“AddHandler”、“RemoveHandler”或“RaiseEvent”方法
语句不提供围绕 `Custom Event` 过程的 `AddHandler`、`RemoveHandler` 或 `RaiseEvent` 声明语句。 自定义事件是包含在 `Custom Event` 和 `End Event` 语句中的代码块。 在此块中，每个 `Custom Event` 过程显示为包含在声明语句和 `End` 语句中的内部块。  
  
 **错误 ID：**BC31113  
  
### 更正此错误  
  
-   提供 `AddHandler`、`RemoveHandler` 或 `RaiseEvent` 声明语句。  
  
## 请参阅  
 [Event 语句](/dotnet/visual-basic/language-reference/statements/event-statement)   
 [AddHandler \- delete](http://msdn.microsoft.com/zh-cn/fc464cf8-582c-48a6-a9c2-185c4c3d5ff8)   
 [RemoveHandler \- delete](http://msdn.microsoft.com/zh-cn/35c17f61-6e22-4b87-b6e1-3ed0c27a88a0)   
 [RaiseEvent \- delete](http://msdn.microsoft.com/zh-cn/7f765da0-5491-40b6-9ed5-24c98f9daad9)   
 [事件](/dotnet/visual-basic/programming-guide/language-features/events/events)
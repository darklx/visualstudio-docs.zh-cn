---
title: "缺少事件“&lt;eventname&gt;”的“RaiseEvent”定义 | Microsoft Docs"
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
  - "vbc31132"
  - "bc31132"
helpviewer_keywords: 
  - "BC31132"
ms.assetid: 8f3442fd-2ed1-4dbc-83a8-f0860ec022ac
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 缺少事件“&lt;eventname&gt;”的“RaiseEvent”定义
如果事件被声明为 `Custom`，它必须提供用于引发该事件的过程。  
  
 **错误 ID：**BC31132  
  
### 更正此错误  
  
1.  在 `Custom Event` 语句和 `End Event` 语句之间包括 `RaiseEvent` 声明。  
  
2.  验证事件声明中的其他过程是否正确终止。  
  
## 请参阅  
 [RaiseEvent 语句](/dotnet/visual-basic/language-reference/statements/raiseevent-statement)   
 [Event 语句](/dotnet/visual-basic/language-reference/statements/event-statement)
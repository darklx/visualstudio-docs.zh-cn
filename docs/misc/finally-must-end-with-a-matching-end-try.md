---
title: "&quot;Finally&quot; 必须以匹配的 &quot;End Try&quot; 结束 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30442"
  - "bc30442"
helpviewer_keywords: 
  - "BC30442"
ms.assetid: 36cce657-186c-4ba0-a760-abcef9529f18
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;Finally&quot; 必须以匹配的 &quot;End Try&quot; 结束
代码中出现的 `Finally` 语句没有匹配的 `End Try`语句。`Finally` 语句必须以 `End Try` 语句结束。  
  
 **错误 ID：**BC30442  
  
### 更正此错误  
  
1.  删除 `Finally` 语句。  
  
2.  添加 `End Try` 语句来结束块。  
  
## 请参阅  
 [Try...Catch...Finally 语句](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)   
 [Visual Basic 的结构化异常处理概述](http://msdn.microsoft.com/zh-cn/bb81af80-a735-4873-9711-6151a48e418a)
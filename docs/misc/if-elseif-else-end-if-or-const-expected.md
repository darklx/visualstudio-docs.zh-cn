---
title: "应为“If”、“ElseIf”、“Else”、“End If”或“Const” | Microsoft Docs"
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
  - "vbc30248"
  - "bc30248"
helpviewer_keywords: 
  - "BC30248"
ms.assetid: fa3bf591-8036-459c-8c29-ed7784e444f6
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 应为“If”、“ElseIf”、“Else”、“End If”或“Const”
源行以 `#` 字符开头，但有效的条件编译指令没有紧跟 `#`。 有效指令包含 `#Const`、`#ExternalSource`、`#If`、`#Else`、`#ElseIf`、`#End If` 和 `#Region`。  
  
 **错误 ID：**BC30248  
  
### 更正此错误  
  
1.  请确保条件编译指令的拼写正确。  
  
2.  请确保 `#` 字符和该指令之间没有干预空格。  
  
3.  删除 `#` 字符或紧跟在其后添加一个有效的指令。  
  
## 请参阅  
 [指令](/dotnet/visual-basic/language-reference/directives/directives)
---
title: "“ElseIf”前面必须是匹配的“If”或“ElseIf” | Microsoft Docs"
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
  - "bc36005"
  - "vbc36005"
helpviewer_keywords: 
  - "BC36005"
ms.assetid: bcebae85-b438-4839-bada-2f8f8dcc8a86
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “ElseIf”前面必须是匹配的“If”或“ElseIf”
出现 `ElseIf` 语句而没有相应的 `If` 语句。`ElseIf` 前面必须是 `If` 语句或另一个 `ElseIf` 语句。  
  
 **错误 ID：**BC36005  
  
### 更正此错误  
  
1.  如果此 `If` 块是一组嵌套控制结构的一部分，请确保正确终止每个结构。  
  
2.  验证 `If` 中嵌套的其他控制结构是否被正确终止。  
  
3.  确保此 `If` 块的格式正确。  
  
## 请参阅  
 [If...Then...Else 语句](/dotnet/visual-basic/language-reference/statements/if-then-else-statement)   
 [决策结构](/dotnet/visual-basic/programming-guide/language-features/control-flow/decision-structures)
---
title: "“&lt;specifier&gt;”在成员变量声明中无效 | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30235"
  - "bc30235"
helpviewer_keywords: 
  - "BC30235"
ms.assetid: 8c5764e4-0096-4ca0-8656-05341a39833a
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “&lt;specifier&gt;”在成员变量声明中无效
`Dim` 语句包含无效的关键字。`Dim` 语句只能包含 `Friend`、`Private`、`Protected`、`Public`、`ReadOnly`、`Shadows`、`Shared` 或 `Static` 关键字。  
  
 如果在过程外声明 `Static` 变量，则也将出现此消息。 仅可在过程级别使用 `Static`。  
  
 请注意，如果在 `Dim` 语句中包含有效的关键字，即可选择性地省略 `Dim` 关键字。  
  
 **错误 ID：**BC30235  
  
### 更正此错误  
  
1.  从 `Dim` 语句中删除无效的关键字。  
  
2.  如果你在过程外声明了 `Static` 变量，请将该声明移动到过程内或删除 `Static` 关键字。  
  
## 请参阅  
 [Dim 语句](/dotnet/visual-basic/language-reference/statements/dim-statement)
---
title: "无法用“MyClass”调用“MustOverride”方法“&lt;methodname&gt;”。 | Microsoft Docs"
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
  - "bc30614"
  - "vbc30614"
helpviewer_keywords: 
  - "BC30614"
ms.assetid: fc57af41-1552-46d1-9727-341f1835e661
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 无法用“MyClass”调用“MustOverride”方法“&lt;methodname&gt;”。
`MyClass` 等效于 `Me`，但其上的所有方法调用都被看作正在调用的方法是 `NotOverridable`。  
  
 **错误 ID：**BC30614  
  
### 更正此错误  
  
-   删除 `MustOverride` 修饰符，或声明基类中的方法并继承和替代该类。  
  
## 请参阅  
 [MustOverride](/dotnet/visual-basic/language-reference/modifiers/mustoverride)   
 [MustInherit](/dotnet/visual-basic/language-reference/modifiers/mustinherit)   
 [NotOverridable](/dotnet/visual-basic/language-reference/modifiers/notoverridable)
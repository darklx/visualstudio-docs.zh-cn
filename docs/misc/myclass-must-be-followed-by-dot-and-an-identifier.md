---
title: "“MyClass”的后面必须跟有“.”和标识符 | Microsoft Docs"
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
  - "bc32028"
  - "vbc32028"
helpviewer_keywords: 
  - "BC32028"
ms.assetid: a7e92b54-32b8-4072-9576-632942f05e0f
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “MyClass”的后面必须跟有“.”和标识符
`MyClass` 不是真正的对象变量，不能单独出现。 在基类中将其视为 `NotOverridable`，只能用于访问当前实例的成员。  
  
 **错误 ID：**BC32028  
  
### 更正此错误  
  
1.  如果你想访问类成员，请在 `MyClass` 之后指定成员访问运算符 \(`.`\) 和当前实例的成员。  
  
2.  如果不想访问类成员，请使用 `Me` 关键字。  
  
## 请参阅  
 [MyClass \- 删除](http://msdn.microsoft.com/zh-cn/5db36f9b-f796-4b6a-ba34-cac1fde6eb62)   
 [Me](http://msdn.microsoft.com/zh-cn/a65973c7-cf06-4547-9b25-9fba885525c2)   
 [NotOverridable](/dotnet/visual-basic/language-reference/modifiers/notoverridable)   
 [继承的基础知识](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)
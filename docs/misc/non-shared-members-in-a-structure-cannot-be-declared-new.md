---
title: "结构中的非共享成员不能声明为“New” | Microsoft Docs"
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
  - "vbc30795"
  - "BC30795"
helpviewer_keywords: 
  - "BC30795"
ms.assetid: 8e4e1ad8-3bac-475f-82e8-e4f134692204
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 结构中的非共享成员不能声明为“New”
使用 `New` 子句声明了结构中的某个非共享变量。  
  
 你可以在结构中对共享引用变量进行初始化，也可以在不初始化的情况下拥有非共享引用变量，如下面的代码行所示。  
  
 `Shared structVar1 As New System.ApplicationException`  
  
 `Dim structVar2 As System.ApplicationException`  
  
 但是，不能在结构中对非共享引用变量进行初始化。 下面的代码行无效。  
  
 `Dim structVar3 As New System.ApplicationException ' INVALID IN A STRUCTURE`  
  
 **错误 ID：**BC30795  
  
### 更正此错误  
  
-   从引用变量声明中删除 `Shared` 修饰符或 `New` 关键字。  
  
## 请参阅  
 [Structure 语句](/dotnet/visual-basic/language-reference/statements/structure-statement)   
 [Shared](/dotnet/visual-basic/language-reference/modifiers/shared)   
 [New 运算符](/dotnet/visual-basic/language-reference/operators/new-operator)
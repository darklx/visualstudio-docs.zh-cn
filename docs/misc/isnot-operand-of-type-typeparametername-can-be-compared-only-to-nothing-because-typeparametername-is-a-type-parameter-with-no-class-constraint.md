---
title: "“&lt;typeparametername&gt;”是没有类约束的类型形参，因此类型“&lt;typeparametername&gt;”的“IsNot”操作数只能与“Nothing”比较 | Microsoft Docs"
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
  - "vbc32097"
  - "bc32097"
helpviewer_keywords: 
  - "BC32097"
ms.assetid: 50283a4b-70e3-4e59-9b9b-65e7cacf5ce1
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “&lt;typeparametername&gt;”是没有类约束的类型形参，因此类型“&lt;typeparametername&gt;”的“IsNot”操作数只能与“Nothing”比较
如果定义的类型形参在其约束列表中没有 [Class \(Visual Basic\)](http://msdn.microsoft.com/zh-cn/0777c6e6-46bc-451b-ad70-57b49d4ef4f7) 关键字或特定类名，则该类型形参可以用作 [IsNot 运算符](/dotnet/visual-basic/language-reference/operators/isnot-operator) 的操作数。  
  
 `IsNot` 比较两个引用类型以确定它们是否指向内存中不同对象实例。 它无法接受非引用类型的操作数，除非另一个操作数是 [Nothing](/dotnet/visual-basic/language-reference/nothing)。  
  
 **错误 ID：**BC32097  
  
### 更正此错误  
  
-   如果你可以要求提供给此类型形参的类型实参始终是引用类型，请将 `Class` 关键字或特定的类名称添加到该类型形参的约束列表中。  
  
-   如果你不能要求提供给此类型形参的类型实参始终是引用类型，请将其从 `IsNot` 表达式中删除。 不能使用 `IsNot` 运算符将其与其他引用类型进行比较。  
  
## 请参阅  
 [Visual Basic 中的泛型类型](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [类型列表](/dotnet/visual-basic/language-reference/statements/type-list)   
 [值类型和引用类型](/dotnet/visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types)   
 [比较运算符 \(Visual Basic\)](/dotnet/visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators)
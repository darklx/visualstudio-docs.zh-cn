---
title: "编译器错误 CS0217 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0217"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0217"
ms.assetid: ede61095-6e11-4f4a-8e7d-85e7a3f4fc3d
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0217
为了可以像短路运算符一样应用，用户定义的逻辑运算符 \(“operator”\) 的返回类型必须与它的两个参数的类型相同。  
  
 如果为用户定义的类型定义运算符，然后尝试将运算符用作短路运算符，则用户定义的运算符必须具有类型相同的参数和返回值。 有关短路运算符的详细信息，请参阅 [&& 运算符](/dotnet/csharp/language-reference/operators/conditional-and-operator)和 [&#124;&#124; 运算符](../Topic/%7C%7C%20Operator%20\(C%23%20Reference\).md)。  
  
 以下示例生成CS0217：  
  
```  
// CS0217.cs using System; public class MyClass { public static bool operator true (MyClass f) { return false; } public static bool operator false (MyClass f) { return false; } public static implicit operator int(MyClass x) { return 0; } public static int operator & (MyClass f1, MyClass f2)   // CS0217 // try the following line instead // public static MyClass operator & (MyClass f1, MyClass f2) { return new MyClass(); } public static void Main() { MyClass f = new MyClass(); int i = f && f; } }  
```  
  
## 请参阅  
 [可重载运算符](/dotnet/csharp/programming-guide/statements-expressions-operators/overloadable-operators)
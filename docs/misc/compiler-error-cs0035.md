---
title: "编译器错误 CS0035 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0035"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0035"
ms.assetid: a622113e-98a4-4583-992c-1fb55139320a
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0035
运算符“operator”对于“type”类型的操作数具有二义性  
  
 编译器有多个可用的转换，但在应用运算符之前不知道选择哪一个。 有关详细信息，请参阅[模板化用户定义的转换](../misc/templated-user-defined-conversions.md)和[转换运算符](/dotnet/csharp/programming-guide/statements-expressions-operators/conversion-operators)。  
  
 下面的示例生成 CS0035：  
  
```  
// CS0035.cs class MyClass { private int i; public MyClass(int i) { this.i = i; } public static implicit operator double(MyClass x) { return (double) x.i; } public static implicit operator decimal(MyClass x) { return (decimal) x.i; } } class MyClass2 { static void Main() { MyClass x = new MyClass(7); object o = - x;   // CS0035 // try a cast: // object o = - (double)x; } }  
  
```
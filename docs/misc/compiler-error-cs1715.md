---
title: "编译器错误 CS1715 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1715"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1715"
ms.assetid: 740044d1-a61c-4156-bc6a-adf26c7499ec
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS1715
“Type1”：类型必须为“Type2”才能匹配重写的成员“MemberName”  
  
 此错误与 [编译器错误 CS0508](../misc/compiler-error-cs0508.md) 相同，区别在于 CS0508 目前仅适用于具有返回类型的方法，而 CS1715 适用于仅具有“类型”而非“返回类型”的属性和索引器。  
  
## 示例  
 下面的代码生成 CS1715。  
  
```  
// CS1715.cs abstract public class Base { abstract public int myProperty { get; set; } } public class Derived : Base { int myField; public override double myProperty  // CS1715 // try the following line instead // public override int myProperty { get { return myField; } set { myField;= value; } } public static void Main() { Derived d = new Derived(); d.myProperty = 5; } }  
```
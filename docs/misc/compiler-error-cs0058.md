---
title: "编译器错误 CS0058 | Microsoft Docs"
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
  - "CS0058"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0058"
ms.assetid: 9535da60-03b9-41ab-93e1-e57b6440fca9
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0058
可访问性不一致: 返回类型“type”的可访问性低于委托“delegate”  
  
 公共构造必须返回可以公开访问的对象。 有关更多信息，请参见[访问修饰符](/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers)。  
  
 下面的示例生成 CS0058，因为没有访问修饰符应用于 MyClass，因此默认授予它私有可访问性：  
  
```  
// CS0058.cs class MyClass // try the following line instead // public class MyClass { } public delegate MyClass MyClassDel();   // CS0058 public class A { public static void Main() { } }  
```  
  
## 请参阅  
 [private](/dotnet/csharp/language-reference/keywords/private)
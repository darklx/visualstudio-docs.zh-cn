---
title: "编译器警告（等级 2）CS0114 | Microsoft Docs"
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
  - "CS0114"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0114"
ms.assetid: 9647772b-d581-4620-981e-f9c607d4a1af
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器警告（等级 2）CS0114
“function1”隐藏继承的成员“function2”。 要使当前方法重写该实现，请添加 override 关键字。 否则请添加 new 关键字。  
  
 类中的声明与基类中的声明冲突，从而使基类成员隐藏。  
  
 有关详细信息，请参阅 [base](/dotnet/csharp/language-reference/keywords/base)。  
  
 下面的示例生成 CS0114：  
  
```  
// CS0114.cs // compile with: /W:2 /warnaserror abstract public class clx { public abstract void f(); } public class cly : clx { public void f() // CS0114, hides base class member // try the following line instead // override public void f() { } public static void Main() { } }  
```
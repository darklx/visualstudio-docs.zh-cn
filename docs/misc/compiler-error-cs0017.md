---
title: "编译器错误 CS0017 | Microsoft Docs"
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
  - "CS0017"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0017"
ms.assetid: 5e2a3eb3-6f6e-485d-8293-ceabea4d6905
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0017
程序“输出文档名称”定义了多个入口点。 请使用 \/main 进行编译，以指定包含入口点的类型。  
  
 一个程序只能有一个 [Main](/dotnet/csharp/programming-guide/main-and-command-args/main-and-command-line-arguments) 方法。  
  
 若要解决此错误，你可以在代码中删除所有 Main 方法，仅保留一个，或者可以使用 [\/main](/dotnet/csharp/language-reference/compiler-options/main-compiler-option) 编译器选项来指定想要使用的 Main 方法。  
  
 下面的示例生成 CS0017：  
  
```  
// CS0017.cs // compile with: /target:exe public class clx { static public void Main() { } } public class cly { public static void Main()   // CS0017, delete one Main or use /main { } }  
```
---
title: "编译器错误 CS1530 | Microsoft Docs"
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
  - "CS1530"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1530"
ms.assetid: 3844b5ef-e0ec-42df-9267-72689020f128
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS1530
不允许在命名空间中定义的元素上使用关键字“new”  
  
 无需在 [namespace](/dotnet/csharp/language-reference/keywords/namespace) 中的任何构造上均指定 [new](/dotnet/csharp/language-reference/keywords/new) 关键字。  
  
 下面的示例生成 CS1530：  
  
```  
// CS1530.cs namespace a { new class i   // CS1530 { } // try the following instead class ii { public static void Main() { } } }  
```
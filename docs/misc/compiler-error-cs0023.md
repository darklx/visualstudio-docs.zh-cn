---
title: "编译器错误 CS0023 | Microsoft Docs"
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
  - "CS0023"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0023"
ms.assetid: 7a30073c-99de-41fa-ac6d-4a0dfbb76de9
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0023
运算符“operator”无法应用于“type”类型的操作数  
  
 尝试将运算符应用于类型没有被设计用于该运算符的变量。 有关详细信息，请参阅[类型](/dotnet/csharp/programming-guide/types/index)和[C\# 运算符](/dotnet/csharp/language-reference/operators/index)。  
  
 下面的示例生成 CS0023：  
  
```  
// CS0023.cs namespace x { public class a { public static void Main() { string s = "hello"; s = -s;   // CS0023, minus operator not allowed on strings } } }  
```
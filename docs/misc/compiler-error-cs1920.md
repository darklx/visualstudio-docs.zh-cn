---
title: "编译器错误 CS1920 | Microsoft Docs"
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
  - "CS1920"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1920"
ms.assetid: efb4782f-a222-4fb5-9e79-8bd2d380520b
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS1920
元素初始值设定项不能为空。  
  
 集合初始值设定项包含一个元素初始值设定项的序列。 元素初始值设定项不需要包含在大括号中，除非其包含赋值表达式。 但是，如果提供有大括号，则它们不能为空。 如果元素初始值设定项是对象初始值设定项，只要该初始值设定项包含新的对象创建表达式，大括号可能为空。  
  
### 更正此错误  
  
-   在大括号之间添加缺少的表达式。  
  
-   如果表达式用作对象初始值设定项，请将新对象创建表达式添加到大括号前面。  
  
## 示例  
 以下示例生成 CS1920：  
  
```  
// cs1920.cs using System.Collections.Generic; public class Test { public static int Main() { // Error. Empty initializer // for inner list. List<List<int>> collection = new List<List<int>>() { { } }; // CS1920 // OK. No initializer for inner list. List<List<int>> collection2 = new List<List<int>>() {  }; // OK. Inner list is initialized // to one List<int> with zero elements. List<List<int>> collection3 = new List<List<int>>() { new List<int> { } }; return 0; } }  
```  
  
## 请参阅  
 [对象和集合初始值设定项](/dotnet/csharp/programming-guide/classes-and-structs/object-and-collection-initializers)
---
title: "编译器错误 CS0742 | Microsoft Docs"
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
  - "CS0742"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0742"
ms.assetid: 078ee7af-17e4-4572-8fee-d97e09c9002b
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0742
查询正文必须以 select 或 group 子句结尾  
  
 查询表达式必须以不包含继续符的 `select` 子句或 `group` 子句结尾。  
  
### 更正此错误  
  
1.  向查询中添加一个 [select 子句](/dotnet/csharp/language-reference/keywords/select-clause)或 [group 子句](/dotnet/csharp/language-reference/keywords/group-clause)。  
  
## 示例  
 下面的代码生成 CS0742：  
  
```  
// cs0742.cs using System.Linq; public class Test { public static int Main() { int[] array = { 1, 2, 3 }; var query = from num in array; // CS0742 return 1; } }  
```  
  
 如果 `group` 子句使用 [into](/dotnet/csharp/language-reference/keywords/into) 关键字将分组结果存储到临时标识符中，则它不能用作查询中的最后一个子句。 仍需要使用 `select` 或另一个 `group` 子句。  
  
## 请参阅  
 [LINQ 查询表达式](/dotnet/csharp/programming-guide/linq-query-expressions/index)
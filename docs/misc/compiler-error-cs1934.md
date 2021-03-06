---
title: "编译器错误 CS1934 | Microsoft Docs"
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
  - "CS1934"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1934"
ms.assetid: 18624be3-d534-4695-bafd-cc664fcde15e
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS1934
未能找到源类型“type”的查询模式的实现。 找不到“method”。 请考虑显式指定范围变量“name”的类型。  
  
 如果查询表达式指定了一个数据源，而没有标准查询运算符对其进行实现，则会生成此错误。 指定了 `ArrayList`，但没有为该范围变量给定显式类型，也会产生此错误。  
  
### 更正此错误  
  
1.  在以下示例中，该解决方案将只指定范围变量的类型：  
  
    ```  
    var q = from int x in list  
    ```  
  
## 示例  
 以下示例演示了生成 CS1934 的一种方式：  
  
```  
// cs1934.cs using System.Linq; using System.Collections; static class Test { public static void Main() { var list = new ArrayList { 0, 1, 2, 3, 4, 5 }; var q = from x in list // CS1934 select x + 1; } }  
```  
  
## 请参阅  
 [How to: Query an ArrayList with LINQ](../Topic/How%20to:%20Query%20an%20ArrayList%20with%20LINQ.md)
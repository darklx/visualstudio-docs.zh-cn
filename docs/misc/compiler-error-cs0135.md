---
title: "编译器错误 CS0135 | Microsoft Docs"
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
  - "CS0135"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0135"
ms.assetid: 1bda402c-e8bd-4117-93d9-f4968d9e8303
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0135
“declaration1”与声明“declaration2”冲突  
  
 编译器不允许隐藏名称，这通常会导致代码中的逻辑错误。  
  
## 示例  
 下面的示例生成 CS0135：  
  
```  
// CS0135.cs  
public class MyClass2  
{  
   public static int i = 0;  
  
   public static void Main()  
   {  
      {  
         int i = 4;  
         i++;  
      }  
      i = 0;   // CS0135  
   }  
}  
```  
  
 来自第 7.5.2.1 节中的 [C\# 语言规范](/dotnet/csharp/language-reference/language-specification)：  
  
 对于表达式或声明符中以简单名称形式给定的标识符的每个匹配项，直接封闭局部变量声明空间 \(§3.3\) 内的表达式或声明符中与简单名称相同的标识符的其他每个匹配项都必须引用同一个实体。 此规则可确保名称的含义在给定的块、switch 块、for\-、foreach\- 或 using\- 语句或匿名函数中始终相同。
---
title: "编译器错误 CS0119 | Microsoft Docs"
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
  - "CS0119"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0119"
ms.assetid: 048924f1-378f-4021-bd20-299d3218f810
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0119
“construct1\_name”是“construct1”，在指定上下文中无效。  
  
 编译器检测到了以下意外构造:  
  
-   类构造函数不是条件语句中的有效测试表达式。  
  
-   使用了类名而不是实例名来引用数组元素。  
  
-   将方法标识符视为结构或类使用  
  
## 示例  
 下面的示例生成 CS0119。  
  
```  
// CS0119.cs using System; public class MyClass { public static void Test() {} public static void Main() { Console.WriteLine(Test.x);   // CS0119 } }  
```
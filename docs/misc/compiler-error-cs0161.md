---
title: "编译器错误 CS0161 | Microsoft Docs"
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
  - "CS0161"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0161"
ms.assetid: c2731a6c-0285-4558-9e62-a7fd480ab0cf
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0161
“method”：并非所有的代码路径都返回值  
  
 返回一个值的方法必须在全部代码路径中具有 `return` 语句。 有关详细信息，请参阅[方法](/dotnet/csharp/programming-guide/classes-and-structs/methods)。  
  
 以下示例生成 CS0161：  
  
```  
// CS0161.cs public class Test { public static int Main() // CS0161 { int i = 10; if (i < 10) { return i; } else { // uncomment the following line to resolve // return 1; } } }  
```
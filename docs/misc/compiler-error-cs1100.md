---
title: "编译器错误 CS1100 | Microsoft Docs"
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
  - "CS1100"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1100"
ms.assetid: ea233371-36b6-49ae-a98c-a00ee3b79e53
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS1100
方法“name”具有一个不在第一个参数上的“this”参数修饰符。  
  
 `this` 修饰符仅允许用于方法的第一个参数，这将向编译器显示该方法是一个扩展方法。  
  
### 更正此错误  
  
1.  除了此方法的第一个参数外，从其他所有参数删除 `this` 修饰符。  
  
## 示例  
 下面的代码生成 CS1100，因为 `this`  参数在修改第二个参数:  
  
```  
// cs1100.cs static class Test { static void ExtMethod(int i, this Test c) // CS1100 { } }  
```  
  
## 请参阅  
 [扩展方法](/dotnet/csharp/programming-guide/classes-and-structs/extension-methods)
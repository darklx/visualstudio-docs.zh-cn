---
title: "编译器错误 CS0594 | Microsoft Docs"
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
  - "CS0594"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0594"
ms.assetid: a3d6bde1-db63-4c5c-a425-8c6a39e00999
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0594
浮点常量超出“type”类型的范围  
  
 分配给浮点变量的值对于此数据类型的变量而言过大。 请参阅[整型表](/dotnet/csharp/language-reference/keywords/integral-types-table)以获取有关数据类型中允许的值范围的信息。  
  
 以下示例生成 CS0594：  
  
```  
// CS0594.cs namespace MyNamespace { public class MyClass { public static void Main() { float f = 6.77777777777E400;   // CS0594, value too large } } }  
```
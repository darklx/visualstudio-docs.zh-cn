---
title: "编译器错误 CS1599 | Microsoft Docs"
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
  - "CS1599"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1599"
ms.assetid: 4cdb282d-0f5d-459b-afc1-8980fbb22067
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS1599
方法或委托不能返回“type”类型  
  
 .NET Framework 类库中的某些类型（例如 <xref:System.TypedReference>、<xref:System.RuntimeArgumentHandle> 和 <xref:System.ArgIterator>）不能用作返回类型，因为它们可能被用于执行不安全的操作。  
  
 下面的示例生成 CS1599：  
  
```  
// CS1599.cs using System; class MyClass { public static void Main() { } public TypedReference Test1()   // CS1599 { return null; } public ArgIterator Test2()   // CS1599 { return null; } }  
```
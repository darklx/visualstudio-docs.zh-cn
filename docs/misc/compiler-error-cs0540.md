---
title: "编译器错误 CS0540 | Microsoft Docs"
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
  - "CS0540"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0540"
ms.assetid: 2da2cd4a-0ff1-45ea-bb72-ea078bc95dea
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0540
“interface member”：包含类型不实现接口“interface”  
  
 你试图在非派生自[接口](/dotnet/csharp/language-reference/keywords/interface)的[类](/dotnet/csharp/language-reference/keywords/class)中实现接口成员。 应删除接口成员的实现，或将接口添加到类的基类列表。  
  
## 示例  
 下面的示例生成 CS0540。  
  
```  
// CS0540.cs interface I { void m(); } public class Clx { void I.m() {}   // CS0540 } // OK public class Cly : I { void I.m() {} public static void Main() {} }  
```  
  
## 示例  
 下面的示例生成 CS0540。  
  
```  
// CS0540_b.cs using System; class C { void IDisposable.Dispose() {}   // CS0540 } class D : IDisposable { void IDisposable.Dispose() {} public void Dispose() {} static void Main() { using (D d = new D()) {} } }  
```
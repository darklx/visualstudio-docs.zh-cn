---
title: "编译器警告（等级 1）CS1957 | Microsoft Docs"
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
  - "CS1957"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1957"
ms.assetid: a4823211-52ce-4ffa-b19b-ee874069409f
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器警告（等级 1）CS1957
成员“name”重写”method”。 在运行时有多个重写候选项。 其实现取决于将要调用的方法。  
  
 仅因是 `ref` 还是 `out` 而异的方法参数在运行时无法区分。  
  
### 避免此警告  
  
1.  为方法之一给定其他名称或其他数目的参数。  
  
## 示例  
 下面的代码生成 CS1957：  
  
```  
// cs1957.cs class Base<T, S> { public virtual string Test(out T x) // CS1957 { x = default(T); return "Base.Test"; } public virtual void Test(ref S x) { } } class Derived : Base<int, int> { public override string Test(out int x) { x = 0; return "Derived.Test"; } static int Main() { int x; if (new Derived().Test(out x) == "Derived.Test") return 0; return 1; } }  
```
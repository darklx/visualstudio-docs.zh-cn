---
title: "编译器错误 CS1014 | Microsoft Docs"
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
  - "CS1014"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1014"
ms.assetid: 60c1e9af-5a0d-4ae0-a2e6-881b0d1535e9
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS1014
应为 get 或 set 访问器  
  
 在属性声明中找到了一个方法声明。 在属性中只能声明 `get` 和 `set` 方法。  
  
 有关属性的详细信息，请参阅 [使用属性](/dotnet/csharp/programming-guide/classes-and-structs/using-properties)。  
  
## 示例  
 下面的示例生成 CS1014。  
  
```  
// CS1014.cs // compile with: /target:library class Sample { public int TestProperty { get { return 0; } int z;   // CS1014  not get or set } }  
```
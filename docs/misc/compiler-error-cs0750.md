---
title: "编译器错误 CS0750 | Microsoft Docs"
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
  - "CS0750"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0750"
ms.assetid: 84fb6841-7f47-405a-ae05-95567692f73d
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0750
分部方法不能具有访问修饰符或 virtual、abstract、override、new、sealed 或 extern 修饰符。  
  
 由于其特殊行为，分部方法需遵守其可接受的修饰符相关限制。  
  
### 更正此错误  
  
1.  删除方法声明中未经授权的修饰符。  
  
## 示例  
 下面的示例生成 CS0750：  
  
```  
// cs0750.cs using System; public class Base { protected virtual void PartG() { } protected void PartH() { } protected virtual void PartI() { } } public partial class C:Base { // All these partial method declarations // will generate CS0750. public partial void PartA(); private partial void PartB(); protected partial void PartC(); internal partial void PartD(); virtual partial void PartE(); abstract partial void PartF(); override partial void PartG(); new partial void PartH(); sealed override partial void PartI(); extern partial void PartJ(); public static int Main() { return 1; } }  
```  
  
## 请参阅  
 [分部类和方法](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)
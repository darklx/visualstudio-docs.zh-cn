---
title: "成员“&lt;membername&gt;”与基类型“&lt;basetypename&gt;”中的成员“&lt;membername&gt;”相冲突，因此不应声明为“Overloads”。 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc40021"
  - "vbc40021"
helpviewer_keywords: 
  - "BC40021"
ms.assetid: 2ec72726-ab0e-4545-9c1e-2409eb54482e
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 成员“&lt;membername&gt;”与基类型“&lt;basetypename&gt;”中的成员“&lt;membername&gt;”相冲突，因此不应声明为“Overloads”。
属性或过程使用 [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads) 关键字来使用相同名称重新声明现有属性或过程，但现有属性或过程位于基类中。  
  
 重载用于定义在同一类中属性或过程的多个版本。 除非基类成员已指定了 [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads)，否则不能定义该基类成员的其他版本。  
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的详细信息，请参见 [在 Visual Basic 中配置警告](../ide/configuring-warnings-in-visual-basic.md)。  
  
 **错误 ID：**BC40021  
  
### 更正此错误  
  
-   如果你想要定义基类成员的其他版本并有权访问基类的源代码，请将 [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads) 关键字添加到基类定义。  
  
-   如果你没有对基类的源代码的访问权限，则无法重载派生类中的成员。 删除 `Overloads` 关键字。  
  
-   如果你想替换基类成员而不是定义基类成员的其他版本，请使用 [Overrides](/dotnet/visual-basic/language-reference/modifiers/overrides) 关键字而不是 `Overloads`。  
  
-   如果你想要使用派生类中的新成员来隐藏基类成员，请使用 [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows) 关键字而不是 `Overloads`。  
  
## 请参阅  
 [过程重载](/dotnet/visual-basic/programming-guide/language-features/procedures/procedure-overloading)   
 [继承的基础知识](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)
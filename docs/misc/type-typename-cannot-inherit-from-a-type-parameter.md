---
title: "类型“&lt;typename&gt;”不能从类型形参继承。 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc32055"
  - "vbc32055"
helpviewer_keywords: 
  - "BC32055"
ms.assetid: 97af7cad-6e40-41e3-892d-1fbcbd86356d
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 类型“&lt;typename&gt;”不能从类型形参继承。
类或接口包含指定泛型类型形参的 [Inherits 语句](/dotnet/visual-basic/language-reference/statements/inherits-statement)。  
  
 类型不能从尚未定义的类型继承。 继承涉及到重用基类成员的能力，这反过来又要求这些成员已定义。 泛型类型形参是将由类型实参所提供的特定类型替换的占位符。 因此，类型不能从占位符继承。  
  
 **错误 ID：**BC32055  
  
### 更正此错误  
  
-   如果继承类型必须从另一种类型继承，请使用特定类型而不是类型形参。  
  
-   如果基类型必须由泛型类型形参来表示，则任何其他类型都不能从它继承。 删除 [Inherits 语句](/dotnet/visual-basic/language-reference/statements/inherits-statement)。  
  
## 请参阅  
 [不在生成中：Visual Basic 中的继承](http://msdn.microsoft.com/zh-cn/e5e6e240-ed31-4657-820c-079b7c79313c)   
 [Visual Basic 中的泛型类型](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)
---
title: "“&lt;keyword&gt;”关键字用于重载继承的成员；重载“Sub New”时不要使用“&lt;keyword&gt;”关键字 | Microsoft Docs"
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
  - "vbc32040"
  - "bc32040"
helpviewer_keywords: 
  - "BC32040"
ms.assetid: 39e6ee0d-b8a0-498e-bdaf-a4ceb13892fe
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “&lt;keyword&gt;”关键字用于重载继承的成员；重载“Sub New”时不要使用“&lt;keyword&gt;”关键字
使用 `Overloads` 关键字声明了一个构造函数。  
  
 Visual Basic 不支持继承或重载构造函数。  
  
 **错误 ID：**BC32040  
  
### 更正此错误  
  
-   从所有构造函数声明中删除 `Overloads` 关键字。  
  
## 请参阅  
 [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads)   
 [不在生成中：使用构造函数和析构函数](http://msdn.microsoft.com/zh-cn/548eebe1-86c4-4377-b2f5-447cb8be3d90)
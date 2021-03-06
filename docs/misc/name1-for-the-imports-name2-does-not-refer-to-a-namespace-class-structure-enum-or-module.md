---
title: "导入“&lt;name2&gt;”的“&lt;name1&gt;”不引用命名空间、类、结构、枚举或模块 | Microsoft Docs"
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
  - "vbc30467"
  - "bc30467"
helpviewer_keywords: 
  - "BC30467"
ms.assetid: a4b8a23b-ba1b-44f7-9584-258dd2607581
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 导入“&lt;name2&gt;”的“&lt;name1&gt;”不引用命名空间、类、结构、枚举或模块
你尝试对 `Namespace`、`Class`、`Structure`、`Enum` 或 `Module` 之外的对象使用 `Imports` 语句。`Imports` 语句从被引用项目和程序集导入命名空间名称，或导入与该语句所在模块相同的项目中定义的命名空间名称。  
  
 **错误 ID：**BC30467  
  
### 更正此错误  
  
-   检查你尝试导入的实体，确保它可有效用于 `Imports` 语句。  
  
## 请参阅  
 [Imports 语句（.NET 命名空间和类型）](/dotnet/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type)   
 [引用和 Imports 语句](/dotnet/visual-basic/programming-guide/program-structure/references-and-the-imports-statement)   
 [NIB 如何：使用“添加引用”对话框添加或删除引用](http://msdn.microsoft.com/zh-cn/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)
---
title: "类型“&lt;typename&gt;”的容器“&lt;containername&gt;”未声明为“Public”，因此不能用作特性 | Microsoft Docs"
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
  - "bc31517"
  - "vbc31517"
helpviewer_keywords: 
  - "BC31517"
ms.assetid: 3d1a8f41-8652-4e37-a6bd-40b0ad306c6f
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 类型“&lt;typename&gt;”的容器“&lt;containername&gt;”未声明为“Public”，因此不能用作特性
定义该特性的类或模块没有使用 `Public` 修饰符进行声明。 默认情况下，没有指定访问修饰符的类和模块将声明为 `Friend`。  
  
 **错误 ID：**BC31517  
  
### 更正此错误  
  
1.  为定义特性的类或模块添加 `Public` 修饰符。  
  
## 请参阅  
 [Public](/dotnet/visual-basic/language-reference/modifiers/public)
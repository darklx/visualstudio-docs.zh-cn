---
title: "类型参数“&lt;类型参数名&gt;”与封闭类型的类型参数具有相同的名称 | Microsoft Docs"
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
  - "vbc40048"
  - "bc40048"
helpviewer_keywords: 
  - "BC40048"
ms.assetid: d5428b36-88d3-42c4-a096-cbc7bb9571f2
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 类型参数“&lt;类型参数名&gt;”与封闭类型的类型参数具有相同的名称
泛型类型的类型参数使用与包含的泛型类型的类型参数相同的名称声明。  
  
 在泛型类型的类型形参列表中，每个类型形参的名称必须与以下所有名称均不同：  
  
-   相同类型形参列表中的每个其他类型形参，  
  
-   在任何包含泛型类型的类型形参列表中的每个类型形参，以及  
  
-   泛型类型本身的名称。  
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的信息，请参见 [在 Visual Basic 中配置警告](../ide/configuring-warnings-in-visual-basic.md)。  
  
 **错误 ID：**BC40048  
  
### 更正此错误  
  
-   重命名类型形参，使其有别于此帮助页上的列表中引用的每个名称。  
  
## 请参阅  
 [Visual Basic 中的泛型类型](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [类型列表](/dotnet/visual-basic/language-reference/statements/type-list)
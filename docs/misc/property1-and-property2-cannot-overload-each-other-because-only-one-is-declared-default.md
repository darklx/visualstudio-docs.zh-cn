---
title: "“&lt;property1&gt;”和“&lt;property2&gt;”中只有一个声明为“Default”，因此它们无法相互重载 | Microsoft Docs"
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
  - "bc30361"
  - "vbc30361"
helpviewer_keywords: 
  - "BC30361"
ms.assetid: bac85b32-1a1f-4c43-817c-76e209cfeb8c
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “&lt;property1&gt;”和“&lt;property2&gt;”中只有一个声明为“Default”，因此它们无法相互重载
如果某个属性指定 `Default`，则在该名称上重载的所有属性也必须指定 `Default`。  
  
 **错误 ID：**BC30361  
  
### 更正此错误  
  
-   请确保所有重载的属性均声明为 `Default`。  
  
## 请参阅  
 [重载过程注意事项](/dotnet/visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures)   
 [Default](/dotnet/visual-basic/language-reference/modifiers/default)
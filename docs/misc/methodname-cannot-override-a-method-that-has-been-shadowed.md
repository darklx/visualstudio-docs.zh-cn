---
title: "“&lt;methodname&gt;”不能重写已被隐藏的方法 | Microsoft Docs"
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
  - "vbc31406"
  - "bc31406"
helpviewer_keywords: 
  - "BC31406"
ms.assetid: 08ed11a6-3399-49fa-ac6e-c5df1328a24e
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “&lt;methodname&gt;”不能重写已被隐藏的方法
某个方法试图重写隐藏其他某个成员的方法。  
  
 **错误 ID：**BC31406  
  
### 更正此错误  
  
-   使用 `Shadows` 修饰符重写隐藏成员。  
  
## 请参阅  
 [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows)   
 [Overrides](/dotnet/visual-basic/language-reference/modifiers/overrides)
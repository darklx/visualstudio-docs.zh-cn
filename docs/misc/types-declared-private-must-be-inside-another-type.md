---
title: "声明为“Private”的类型必须在另一个类型内 | Microsoft Docs"
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
  - "vbc31089"
  - "bc31089"
helpviewer_keywords: 
  - "BC31089"
ms.assetid: 44ea5fe4-4af6-4cea-a4a5-2cf966df2937
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 声明为“Private”的类型必须在另一个类型内
在一种类型而不是在另一种类型内使用了 `Private` 修饰符。  
  
 **错误 ID：**BC31089  
  
### 更正此错误  
  
1.  使用限制性较弱的访问修饰符，比如 `Friend`。  
  
2.  在另一种类型中声明该类型。  
  
## 请参阅  
 [Private](/dotnet/visual-basic/language-reference/modifiers/private)
---
title: "“&lt;method1&gt;”和“&lt;method2&gt;”无法相互重载，因为两者的差异仅在于声明为“ParamArray”的参数。 | Microsoft Docs"
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
  - "bc30368"
  - "vbc30368"
helpviewer_keywords: 
  - "BC30368"
ms.assetid: 6111df0c-fc3e-40b2-b536-effbd132ef72
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “&lt;method1&gt;”和“&lt;method2&gt;”无法相互重载，因为两者的差异仅在于声明为“ParamArray”的参数。
试图重载两种方法，它们的差异仅在于 `ParamArray` 参数的个数。 编译器将具有 `ParamArray` 参数的过程视为具有无限数目的重载，且各个重载的差异在于传递给参数数组的内容。  
  
 **错误 ID：**BC30368  
  
### 更正此错误  
  
-   请确保方法不仅由 `ParamArray` 参数进行区分。  
  
## 请参阅  
 [重载过程注意事项](/dotnet/visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures)   
 [参数数组](/dotnet/visual-basic/programming-guide/language-features/procedures/parameter-arrays)
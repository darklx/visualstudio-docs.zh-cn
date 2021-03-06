---
title: "“Class”约束不能为同一类型参数指定多次。 | Microsoft Docs"
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
  - "bc32101"
  - "vbc32101"
helpviewer_keywords: 
  - "BC32101"
ms.assetid: fac2330a-e397-4bd9-8166-934407575f9e
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “Class”约束不能为同一类型参数指定多次。
约束列表多次包括[类 \(Visual Basic\)](http://msdn.microsoft.com/zh-cn/0777c6e6-46bc-451b-ad70-57b49d4ef4f7) 约束。  
  
 类型形参上的约束列表可以指定传递到该类型形参的类型实参必须是值类型（具有[结构 \(Visual Basic\)](http://msdn.microsoft.com/zh-cn/263ce115-ac36-4c05-8cb7-0e0eead5c6d0) 约束）或者必须是引用类型（具有 `Class` 约束）。 不能为同一类型形参同时指定两个约束，并且不能多次指定其中任意一个约束。  
  
 错误 ID：BC32101  
  
### 更正此错误  
  
-   删除任何多余的 `Class` 关键字。 约束列表中只能有一个关键字。  
  
## 请参阅  
 [Visual Basic 中的泛型类型](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [值类型和引用类型](/dotnet/visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types)
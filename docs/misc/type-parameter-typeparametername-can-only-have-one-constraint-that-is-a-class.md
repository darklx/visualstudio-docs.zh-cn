---
title: "类型形参“&lt;typeparametername&gt;”只能具有一个为类的约束 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc32047"
  - "vbc32047"
helpviewer_keywords: 
  - "BC32047"
ms.assetid: ac7ab76b-5300-4c79-b519-5a1287ed5fa9
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 类型形参“&lt;typeparametername&gt;”只能具有一个为类的约束
约束列表包括多个类。  
  
 类型形参上的约束列表可接受任意数量的接口，但最多能接受一个类。 提供给此类型形参的类型实参必须从类中继承，且 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 不支持多重继承。  
  
 **错误 ID：**BC32047  
  
### 更正此错误  
  
-   选择一个类，并使约束列表中只包括此类。  
  
-   你可定义其他类型形参，以容纳不可包含在此约束列表中的一个或多个类。  
  
## 请参阅  
 [Visual Basic 中的泛型类型](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)
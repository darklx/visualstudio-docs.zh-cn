---
title: "“&lt;membername&gt;”存在于多个基接口中 | Microsoft Docs"
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
  - "vbc31040"
  - "bc31040"
helpviewer_keywords: 
  - "BC31040"
ms.assetid: c1a80d64-3986-417f-af92-412183e490ad
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “&lt;membername&gt;”存在于多个基接口中
“\<membername\>”存在于多个基接口中。 请使用在“Implements”子句中声明“\<membername\>”的接口的名称，而不要使用派生接口的名称。  
  
 此接口从多个接口继承具有相同名称的成员，产生了多义性。  
  
 **错误 ID：**BC31040  
  
### 更正此错误  
  
-   使用 `Implements` 子句中的定义接口名称而不是派生接口的名称。  
  
## 请参阅  
 [接口](/dotnet/visual-basic/programming-guide/language-features/interfaces/index)   
 [Implements](/dotnet/visual-basic/language-reference/statements/implements-clause)
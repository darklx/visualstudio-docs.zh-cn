---
title: "“Next”前面必须是匹配的“For” | Microsoft Docs"
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
  - "vbc30092"
  - "bc30092"
helpviewer_keywords: 
  - "BC30092"
ms.assetid: 4bf49bb2-c69b-443d-aa58-cb40fcfb1370
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “Next”前面必须是匹配的“For”
出现 `Next` 语句而没有相应的 `For` 或 `For Each` 语句。`Next` 前面必须有相应的 `For` 或 `For Each` 语句。  
  
 **错误 ID：**BC30092  
  
### 更正此错误  
  
1.  如果此 `For` 循环是一组嵌套 `For` 循环的一部分，请确保每个循环正常终止。  
  
2.  验证 `For` 循环内的其他控制结构是否被正确终止。  
  
3.  确保此 `For` 循环的格式正确。  
  
## 请参阅  
 [For...Next 语句](/dotnet/visual-basic/language-reference/statements/for-next-statement)   
 [For Each...Next 语句](/dotnet/visual-basic/language-reference/statements/for-each-next-statement)
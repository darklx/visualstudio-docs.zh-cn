---
title: "“With”必须以匹配的“End With”结束 | Microsoft Docs"
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
  - "bc30085"
  - "vbc30085"
helpviewer_keywords: 
  - "BC30085"
ms.assetid: aa88f4d0-be5f-4efe-a4ef-80e6d6124e6e
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “With”必须以匹配的“End With”结束
出现 `With` 语句而没有相应的 `End With` 语句。 必须使用 `End With` 语句结束 `With` 块。  
  
 **错误 ID：**BC30085  
  
### 更正此错误  
  
-   如果此 `With` 块属于一组嵌套的 `With` 块，请确保每个块均已正确终止。  
  
-   将 `End With` 语句添加到 `With` 块末尾。  
  
## 请参阅  
 [With...End With 语句](/dotnet/visual-basic/language-reference/statements/with-end-with-statement)
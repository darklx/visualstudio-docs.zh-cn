---
title: "&quot;Exit While&quot; 只能出现在 &quot;While&quot; 语句内 | Microsoft Docs"
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
  - "vbc30097"
  - "bc30097"
helpviewer_keywords: 
  - "BC30097"
ms.assetid: cf0a3e09-5252-4198-bb27-c103c98d9f19
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;Exit While&quot; 只能出现在 &quot;While&quot; 语句内
`Exit While` 语句出现在 `While` 块之外。`Exit While` 仅在 `While` 语句和相应的 `End While` 语句之间有效。  
  
 **错误 ID：**BC30097  
  
### 更正此错误  
  
1.  确保 `Exit While` 之前有一个有效的 `While` 语句，之后有一个有效的 `End While` 语句。  
  
2.  验证 `While` 块中的其他控制结构是否被正确终止。  
  
## 请参阅  
 [While...End While 语句](/dotnet/visual-basic/language-reference/statements/while-end-while-statement)
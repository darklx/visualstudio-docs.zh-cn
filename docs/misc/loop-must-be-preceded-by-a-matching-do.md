---
title: "“Loop”前面必须是匹配的“Do” | Microsoft Docs"
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
  - "vbc30091"
  - "bc30091"
helpviewer_keywords: 
  - "BC30091"
ms.assetid: 05f47b2f-4eaa-4911-981e-3fce737d249f
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “Loop”前面必须是匹配的“Do”
出现 `Loop` 语句而没有相应的 `Do` 语句。`Loop` 前面必须有相应的 `Do` 语句。  
  
 **错误 ID:** BC30091  
  
### 更正此错误  
  
1.  如果此 `Do` 循环是一组嵌套 `Do` 循环的一部分，请确保每个循环正常终止。  
  
2.  验证 `Do` 循环内的其他控制结构是否被正确终止。  
  
3.  确保此 `Do` 循环的格式正确。  
  
## 请参阅  
 [Do...Loop 语句](/dotnet/visual-basic/language-reference/statements/do-loop-statement)
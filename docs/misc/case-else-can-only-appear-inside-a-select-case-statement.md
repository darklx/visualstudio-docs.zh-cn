---
title: "“Case Else”只能出现在“Select Case”语句内 | Microsoft Docs"
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
  - "bc30071"
  - "vbc30071"
helpviewer_keywords: 
  - "BC30071"
ms.assetid: 9a4f8ccb-717a-4d18-91b4-4a373202c38a
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “Case Else”只能出现在“Select Case”语句内
`Case Else` 语句出现在 `Select` 块之外。`Case Else` 语句只能用在 `Select` 语句或 `Select Case` 语句和其对应的 `End Select` 语句之间。  
  
 **错误 ID：**BC30071  
  
### 更正此错误  
  
-   删除 `Case Else` 语句或将其移动到 `Select` 块之内。  
  
## 请参阅  
 [Select...Case 语句](/dotnet/visual-basic/language-reference/statements/select-case-statement)
---
title: "“GoTo”语句在即时窗口中无效 | Microsoft Docs"
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
  - "bc30133"
  - "vbc30133"
helpviewer_keywords: 
  - "BC30133"
ms.assetid: e5901616-6aec-4718-b452-90b2143301b0
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “GoTo”语句在即时窗口中无效
`GoTo` 语句执行分支，但不允许用于调试上下文。  
  
 **错误 ID：**BC30133  
  
### 更正此错误  
  
-   不要在“即时”窗口中发出 `GoTo` 语句。  
  
## 请参阅  
 [即时窗口](../ide/reference/immediate-window.md)
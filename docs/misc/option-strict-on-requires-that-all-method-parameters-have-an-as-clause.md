---
title: "Option Strict On 要求所有方法参数都有“As”子句 | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30211"
  - "bc30211"
helpviewer_keywords: 
  - "BC30211"
ms.assetid: 855795ce-8499-4525-a1de-cbb8ba364cd7
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On 要求所有方法参数都有“As”子句
方法包含未带 `As` 子句的参数。 当 `Option Strict` 处于打开状态时，必须用 `As` 子句来声明每个变量、属性、过程参数和函数返回，以指定其数据类型；例如，`Sub GetData(ByVal filter As String)`。  
  
 **错误 ID：**BC30211  
  
### 更正此错误  
  
-   检查 `As` 关键字是否拼写错误。  
  
-   为已声明的变量提供 `As` 子句，或关闭 `Option Strict`。  
  
## 请参阅  
 [Option Strict 语句](/dotnet/visual-basic/language-reference/statements/option-strict-statement)   
 [Sub 语句](/dotnet/visual-basic/language-reference/statements/sub-statement)   
 [Function 语句](/dotnet/visual-basic/language-reference/statements/function-statement)
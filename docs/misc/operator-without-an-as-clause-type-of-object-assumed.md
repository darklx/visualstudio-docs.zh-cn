---
title: "没有“As”子句的运算符；假定为 Object 类型 | Microsoft Docs"
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
  - "vbc41005"
  - "bc41005"
helpviewer_keywords: 
  - "BC41005"
ms.assetid: 42be84ed-7aa6-4ac0-9dd4-663e90f13e09
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 没有“As”子句的运算符；假定为 Object 类型
运算符过程未指定 `As` 子句。  
  
 `As` 子句标识要与编程元素关联的数据类型。 在 [Operator 语句](/dotnet/visual-basic/language-reference/statements/operator-statement) 中，它指定运算符过程返回到调用代码的值的数据类型。 如果在 `Operator` 语句中不包含 `As` 子句，则返回数据类型默认为 `Object`。  
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的信息，请参见 [在 Visual Basic 中配置警告](../ide/configuring-warnings-in-visual-basic.md)。  
  
 **错误 ID：**BC41005  
  
### 更正此错误  
  
-   在 `Operator` 语句中包含一个 `As` 子句以指定返回数据类型。  
  
## 请参阅  
 [运算符过程](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator 语句](/dotnet/visual-basic/language-reference/statements/operator-statement)
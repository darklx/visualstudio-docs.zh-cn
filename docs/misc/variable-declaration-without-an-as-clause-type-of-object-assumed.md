---
title: "变量声明没有“As”子句；假定为 Object 类型 | Microsoft Docs"
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
  - "BC42020"
  - "vbc42020"
helpviewer_keywords: 
  - "BC42020"
ms.assetid: 9422b16d-39b5-4d49-b697-608226ccafea
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 变量声明没有“As”子句；假定为 Object 类型
变量声明未指定 `As` 子句。  
  
 `As` 子句标识要与编程元素关联的数据类型。 在 [Dim 语句](/dotnet/visual-basic/language-reference/statements/dim-statement) 中，它指定变量的数据类型。 如果在 `Dim` 语句中不包含 `As` 子句，则变量数据类型默认为 `Object`。  
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的信息，请参见 [在 Visual Basic 中配置警告](../ide/configuring-warnings-in-visual-basic.md)。  
  
 **错误 ID：**BC42020  
  
### 更正此错误  
  
-   在 `Dim` 语句中包含一个 `As` 子句以指定变量的数据类型。  
  
## 请参阅  
 [Dim 语句](/dotnet/visual-basic/language-reference/statements/dim-statement)   
 [变量声明](/dotnet/visual-basic/programming-guide/language-features/variables/variable-declaration)
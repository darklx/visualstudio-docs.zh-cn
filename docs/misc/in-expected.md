---
title: "应为“In” | Microsoft Docs"
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
  - "bc36607"
  - "vbc36607"
helpviewer_keywords: 
  - "BC36607"
ms.assetid: f390bca5-12fe-4fe1-bd86-7f8ab66dfbd8
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 应为“In”
已经指定 `From` 或 `Aggregate` 子句，但没有使用 `In` 运算符。 使用 `In` 运算符来标识要查询的集合。  
  
 **错误 ID：**BC36607  
  
### 更正此错误  
  
1.  将 `In` 运算符和键字段添加到 `From` 或 `Aggregate` 子句。 下面是一个示例：  
  
    ```vb#  
    Dim names = From pers In people Select pers.FirstName, pers.LastName  
    ```  
  
## 请参阅  
 [From 子句](/dotnet/visual-basic/language-reference/queries/from-clause)   
 [Aggregate 子句](/dotnet/visual-basic/language-reference/queries/aggregate-clause)   
 [Visual Basic 中的 LINQ 简介](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [LINQ](/dotnet/visual-basic/programming-guide/language-features/linq/index)
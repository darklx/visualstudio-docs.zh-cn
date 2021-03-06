---
title: "运算符“&lt;operator&gt;”必须有两个参数 | Microsoft Docs"
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
  - "bc33015"
  - "vbc33015"
helpviewer_keywords: 
  - "BC33015"
ms.assetid: 506ea996-8abe-4dbe-aff4-d3910bf4399e
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 运算符“&lt;operator&gt;”必须有两个参数
用两个以上或以下的参数定义了二元运算符。  
  
 二元运算符必须有且只有两个参数。  
  
 **错误 ID：**BC33015  
  
### 更正此错误  
  
-   将定义调整为指定恰好两个参数。  
  
-   如果你只需要一个参数，则必须定义一元运算符。  
  
-   如果不需要参数或需要两个以上的参数，则必须使用 [Function 语句](/dotnet/visual-basic/language-reference/statements/function-statement) 来定义 `Function` 过程（而不是运算符）。  
  
## 请参阅  
 [运算符过程](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator 语句](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [如何：定义运算符](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [如何：定义转换运算符](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)
---
title: "“IsNot”需要具有引用类型的操作数，但此操作数具有值类型“&lt;typename&gt;”。 | Microsoft Docs"
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
  - "bc31419"
  - "vbc31419"
helpviewer_keywords: 
  - "BC31419"
ms.assetid: c44d2936-8c07-443a-b320-ac2bfbc1e9ec
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “IsNot”需要具有引用类型的操作数，但此操作数具有值类型“&lt;typename&gt;”。
表达式使用具有至少一个值类型操作数的 [IsNot 运算符](/dotnet/visual-basic/language-reference/operators/isnot-operator)。  
  
 `IsNot` 运算符确定两个对象引用是否引用不同的对象。 它将引用类型的指针值进行比较，且它对于值类型没有意义。  
  
 **错误 ID：**BC31419  
  
### 更正此错误  
  
-   如果你想要比较的两个值类型的值，使用 `=` 或 `<>` 比较运算符。  
  
-   如果你想要比较的两个引用类型的指针，请确保针对两个操作数使用对象引用。 你可以使用引用变量或与引用变量行为方式类似的元素，如 [Me](http://msdn.microsoft.com/zh-cn/a65973c7-cf06-4547-9b25-9fba885525c2) 关键字。  
  
## 请参阅  
 [比较运算符 \(Visual Basic\)](/dotnet/visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators)   
 [如何：测试两个对象是否相同](../Topic/How%20to:%20Test%20Whether%20Two%20Objects%20Are%20the%20Same%20\(Visual%20Basic\).md)
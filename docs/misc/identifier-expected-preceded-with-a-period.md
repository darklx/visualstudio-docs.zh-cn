---
title: "需要有以句点开头的标识符 | Microsoft Docs"
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
  - "bc36576"
  - "vbc36576"
helpviewer_keywords: 
  - "BC36576"
ms.assetid: 02217cc4-8972-4a6d-97a6-4ecbb7399af2
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 需要有以句点开头的标识符
匿名类型声明初始值设定项列表中包含无法推断出属性名称的值，没有为其分配属性名称。  
  
```  
' Not valid. ' Dim anon1 = New With {.grade = 100, 95}  
```  
  
 **错误 ID:** BC36576  
  
### 更正此错误  
  
-   为初始值设定项列表中的每个值提供属性名称，代码如下所示：  
  
    ```  
    Dim anon2 = New With {.grade1 = 100, .grade2 = 95}  
    ```  
  
## 请参阅  
 [对象初始值设定项：命名类型和匿名类型](../Topic/Object%20Initializers:%20Named%20and%20Anonymous%20Types%20\(Visual%20Basic\).md)   
 [如何：声明匿名类型 \(Visual Basic\) 的实例](http://msdn.microsoft.com/zh-cn/119f616c-9bcd-4731-ac00-4285be5959f7)   
 [如何：推断匿名类型声明中的属性名和类型](../Topic/How%20to:%20Infer%20Property%20Names%20and%20Types%20in%20Anonymous%20Type%20Declarations%20\(Visual%20Basic\).md)
---
title: "无法推断“&lt;variablename&gt;”的数据类型，因为数组维数不匹配 | Microsoft Docs"
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
  - "bc36909"
  - "vbc36909"
helpviewer_keywords: 
  - "BC36909"
ms.assetid: e41fec81-efec-4395-a0a5-d81906a2d4f1
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 无法推断“&lt;variablename&gt;”的数据类型，因为数组维数不匹配
如果用于初始化数组的维数与声明中的维数不匹配，则编译器无法推断此数组的数据类型。 例如，下面的代码会导致此错误。  
  
```vb#  
' Valid. exampleArray1 is a one-dimensional array of integers. Dim exampleArray1() = New Integer() {1, 2, 3} ' Not valid. 'Dim exampleArray2(,) = New Integer() {1, 2, 3} 'Dim exampleArray3(,) = New Integer() {}  
```  
  
 **错误 ID：**BC36909  
  
## 请参阅  
 [局部类型推理](/dotnet/visual-basic/programming-guide/language-features/variables/local-type-inference)   
 [NOTINBUILD 如何：初始化多维数组](http://msdn.microsoft.com/zh-cn/502dcf8b-d86c-46f1-ad7d-3ce809645774)
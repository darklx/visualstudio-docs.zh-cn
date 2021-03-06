---
title: "无法为不定维度指定数组初始值设定项；请使用空初始值设定项“{}” | Microsoft Docs"
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
  - "vbc30949"
  - "bc30949"
helpviewer_keywords: 
  - "BC30949"
ms.assetid: b3d27d9c-7a1f-4bac-ad71-388b24b807b3
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 无法为不定维度指定数组初始值设定项；请使用空初始值设定项“{}”
数组对编译时未知的维度进行初始化。  
  
 以下代码生成此错误。  
  
```  
Dim j As Integer Dim intArray As Integer = New Integer(1, j) {{0, 100}, {1,101}}  
```  
  
 以下代码可避免此错误。  
  
```  
Dim intArray As Integer = New Integer(1, j) {} For i As Integer = 0 To j intArray(0, i) = i intArray(1, i) = 100 + i Next i  
```  
  
 **错误 ID：**BC30949  
  
### 更正此错误  
  
-   如果可能，请在数组声明中指定常数维度。  
  
-   如果不能指定常数维度，则当不定维度变为已知时必须使用循环初始化该数组。  
  
## 请参阅  
 [For Each...Next 语句](/dotnet/visual-basic/language-reference/statements/for-each-next-statement)   
 [NOTINBUILD Visual Basic 中的数组概述](http://msdn.microsoft.com/zh-cn/ca50e2f2-b4d2-4c57-9169-9abbcc3392d8)   
 [如何：在 Visual Basic 中初始化数组变量](../Topic/How%20to:%20Initialize%20an%20Array%20Variable%20in%20Visual%20Basic.md)   
 [NOTINBUILD 如何：初始化多维数组](http://msdn.microsoft.com/zh-cn/502dcf8b-d86c-46f1-ad7d-3ce809645774)
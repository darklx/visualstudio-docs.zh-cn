---
title: "在“&lt;typename&gt;”中定义的扩展方法“&lt;methodname&gt;”中的参数“&lt;parametername&gt;”已具有匹配的忽略实参 | Microsoft Docs"
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
  - "bc36583"
  - "vbc36583"
helpviewer_keywords: 
  - "BC36583"
ms.assetid: 662072fa-abb8-43c3-8ca2-aefb20f2e902
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 在“&lt;typename&gt;”中定义的扩展方法“&lt;methodname&gt;”中的参数“&lt;parametername&gt;”已具有匹配的忽略实参
扩展方法的过程调用按位置忽略实参，然后按名称提供实参。 例如，对扩展方法 `ABC` 的以下调用首先忽略参数的实参 `Y`，然后按名称提供。  
  
```  
<Extension()> _ Public Sub ABC(ByVal X As Integer, Optional ByVal Y As Byte = 0, _ Optional ByVal Z As Byte = 0) End Sub ' . . . ' Calling extension method ABC. Dim number As Integer ' Not valid. ' number.ABC(, 4, Y:=5)  
```  
  
 **错误 ID：**BC36583  
  
### 更正此错误  
  
-   按位置提供参数，或删除省略它的逗号。  
  
## 请参阅  
 [扩展方法](/dotnet/visual-basic/programming-guide/language-features/procedures/extension-methods)   
 [按位置和按名称传递参数](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name)
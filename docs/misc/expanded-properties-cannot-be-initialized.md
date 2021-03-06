---
title: "不能初始化扩展属性 | Microsoft Docs"
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
  - "vbc36714"
  - "bc36714"
helpviewer_keywords: 
  - "BC36714"
ms.assetid: ba9408f3-e606-4749-8372-987999f405f5
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 不能初始化扩展属性
可以初始化自动实现的属性作为其声明的一部分，但不能初始化扩展的属性。  
  
 **错误 ID：**BC36714  
  
### 更正此错误  
  
-   使用自动实现的属性，或者从属性声明中删除该初始化。  
  
## 示例  
 下面的示例演示了自动实现的和扩展的属性。 自动实现的属性可通过使用分配或 `New` 子句进行初始化，但扩展的属性不能。  
  
```vb#  
Class AutoImplementedExample ' An auto-implemented property can be assigned an initial value. Property IDNum As Integer = 33542 ' An auto-implemented property can be initialized with New. Property Name As New String("Don Hall") End Class Class ExpandedExample ' Attempting to expand an initialized auto-implemented property ' causes this error. 'Property IDNum As Integer = 33542 '    Get '    End Get '    Set(ByVal value As Integer) '    End Set 'End Property ' Instead, you can assign the initial value to the backing field. Private _IDNum As Integer = 33542 Property IDNum As Integer Get End Get Set(ByVal value As Integer) End Set End Property End Class  
```  
  
## 请参阅  
 [自动实现的属性](/dotnet/visual-basic/programming-guide/language-features/procedures/auto-implemented-properties)   
 [如何：创建属性](../Topic/How%20to:%20Create%20a%20Property%20\(Visual%20Basic\).md)   
 [Property 过程](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)
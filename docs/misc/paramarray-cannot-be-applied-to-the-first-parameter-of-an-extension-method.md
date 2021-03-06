---
title: "“ParamArray”无法应用于扩展方法的第一个参数 | Microsoft Docs"
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
  - "vbc36554"
  - "bc36554"
helpviewer_keywords: 
  - "BC36554"
ms.assetid: 0778a854-246f-4c2b-943d-ea8883b3aa6f
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “ParamArray”无法应用于扩展方法的第一个参数
“ParamArray”无法应用于扩展方法的第一个参数。 第一个参数指定要扩展哪个类型。  
  
 扩展方法的第一个参数指定该方法扩展的数据类型。 因此，第一个参数是必需的，而不能是可选的。 因为形参数组是自动可选的，所以不能作为扩展方法的第一个实参。  
  
> [!NOTE]
>  执行方法时，调用方法的扩展数据类型的实例成为方法的第一个形参的实参。 例如，`greeting.Print()` 中的实例 `greeting` 是扩展方法 `Public Sub Print (ByVal str As String)` 中第一个形参 `str` 的实参。  
  
 **错误 ID：**BC36554  
  
### 更正此错误  
  
-   如果形参数组未指定要扩展的数据类型，请添加新的第一个形参以指定此类型。  
  
    ```  
    <Extension()> Public Sub AddTo(ByRef str As String, ByVal ParamArray addOns() As String) ' Concatenate the strings in addOns to str. End Sub  
    ```  
  
-   如果形参数组指定了要扩展的数据类型，请考虑将其更改为需要实参的常规数组，而不要使用形参数组。 常规数组可以进行扩展。  
  
    ```  
    <Extension()> Public Function Sum(ByVal ints() As Integer) As Integer Dim total As Integer = 0 For Each i As Integer In ints total = total + i Next i Return total End Function  
    ```  
  
## 请参阅  
 [扩展方法](/dotnet/visual-basic/programming-guide/language-features/procedures/extension-methods)   
 [参数数组](/dotnet/visual-basic/programming-guide/language-features/procedures/parameter-arrays)   
 [可选参数](/dotnet/visual-basic/programming-guide/language-features/procedures/optional-parameters)
---
title: "方法参数必须括在圆括号中 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30800"
  - "bc30800"
helpviewer_keywords: 
  - "BC30800"
ms.assetid: ecdec760-8b51-474f-acad-17cf8059d83b
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 方法参数必须括在圆括号中
这些规则控制过程调用在 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 的较新版本更简单。 参数必须括在圆括号中。  
  
 **错误 ID：**BC30800  
  
### 更正此错误  
  
-   将参数列表括在圆括号内；例如：  
  
    ```  
    MySub(ArrayIndex, NewValue)  
    ```  
  
## 请参阅  
 [Procedure Calling Sequence Changes in Visual Basic](http://msdn.microsoft.com/zh-cn/4ef1eea6-36cb-4b97-a31b-9ba65e46a9fd)   
 [过程参数和自变量](/dotnet/visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments)
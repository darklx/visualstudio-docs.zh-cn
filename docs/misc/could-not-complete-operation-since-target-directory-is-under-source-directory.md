---
title: "未能完成操作，因为目标目录位于源目录下 | Microsoft Docs"
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
  - "vbrIO_CyclicOperation"
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 未能完成操作，因为目标目录位于源目录下
循环操作已失败。 循环操作正在循环，因此无法完成。 例如，对象 A 可能会尝试从对象 B 中继承，而后者反之从对象 A 中继承。  
  
### 更正此错误  
  
-   继承时，请确保没有任何循环引用。  
  
## 请参阅  
 [错误类型](/dotnet/visual-basic/programming-guide/language-features/error-types)   
 [Debugging Basics: Breakpoints](http://msdn.microsoft.com/zh-cn/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)
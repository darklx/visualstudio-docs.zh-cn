---
title: "特性常量“&lt;constantname&gt;”不能作为赋值的目标 | Microsoft Docs"
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
  - "bc31510"
  - "vbc31510"
helpviewer_keywords: 
  - "BC31510"
ms.assetid: 5459c531-3a4e-4e03-b185-9c5766254982
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 特性常量“&lt;constantname&gt;”不能作为赋值的目标
尝试给特性中声明的常量赋值。  
  
 **错误 ID：**BC31510  
  
### 更正此错误  
  
-   删除错误的赋值。  
  
-   如果使用自己开发的自定义特性，请将特性中的成员重定义为字段。  
  
## 请参阅  
 [不在生成中：Visual Basic 中的特性](http://msdn.microsoft.com/zh-cn/620bfc0e-4582-4c8b-8432-ebc5c3dccc22)   
 [常量和枚举](/dotnet/visual-basic/language-reference/constants-and-enumerations)
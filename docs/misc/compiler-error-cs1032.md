---
title: "编译器错误 CS1032 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1032"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1032"
ms.assetid: fe318a6c-4403-4b9b-b3d8-753ec31c00ff
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS1032
不能在文件的第一个标记之后定义或取消定义预处理器符号  
  
 `#define` 和 `#undef`[预处理器指令](/dotnet/csharp/language-reference/preprocessor-directives/index)必须用在程序的开头，并且在其他任何关键字之前，例如用在命名空间声明中的那些指令之前。  
  
 下面的示例生成 CS1032：  
  
```  
// CS1032.cs namespace x { public class clx { #define a   // CS1032, put before namespace public static void Main() { } } }  
```
---
title: "编译器错误 CS0139 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0139"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0139"
ms.assetid: 235ba3d4-566c-4ef6-801a-a338f4f2a12d
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0139
没有要中断或继续的封闭循环  
  
 在循环外遇到了一个 break 或 continue 语句。  
  
 有关详细信息，请参阅[跳转语句](/dotnet/csharp/language-reference/keywords/jump-statements)。  
  
 下面的示例生成 CS0139 两次：  
  
```  
// CS0139.cs namespace x { public class a { public static void Main() { continue;  // CS0139 break;     // CS0139 } } }  
```
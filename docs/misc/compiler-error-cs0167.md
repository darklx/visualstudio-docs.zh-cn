---
title: "编译器错误 CS0167 | Microsoft Docs"
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
  - "CS0167"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0167"
ms.assetid: e6901b40-11a0-422c-9ea3-3b25c0ad7791
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0167
委托“delegate”缺少 Invoke 方法  
  
 你导入并使用了用另一编译器创建的托管程序（即使用 .NET Framework 公共语言运行时的托管程序）。 此编译器允许了格式错误的 [delegate](/dotnet/csharp/language-reference/keywords/delegate)。 因此，`Invoke` 方法不可用。 有关详细信息，请参阅[委托](/dotnet/csharp/programming-guide/delegates/index)。
---
title: "接口中的枚举不能声明为“&lt;specifier&gt;” | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31069"
  - "bc31069"
helpviewer_keywords: 
  - "BC31069"
ms.assetid: 26025ba0-c710-4fd4-8f36-f931db142d96
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 接口中的枚举不能声明为“&lt;specifier&gt;”
使用在接口中声明的枚举指定了无效的修饰符。  
  
 **错误 ID：**BC31069  
  
### 更正此错误  
  
-   删除修饰符，如 `Public`、`Private`、`Shared`、`Friend`、`Protected`、`Protected Friend` 或 `Overridable`。  
  
## 请参阅  
 [接口](/dotnet/visual-basic/programming-guide/language-features/interfaces/index)   
 [Enum 语句](/dotnet/visual-basic/language-reference/statements/enum-statement)
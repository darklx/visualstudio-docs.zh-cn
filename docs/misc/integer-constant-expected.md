---
title: "应为整数常量 | Microsoft Docs"
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
  - "bc30204"
  - "vbc30204"
helpviewer_keywords: 
  - "BC30204"
ms.assetid: e8d2fe24-7e63-4c30-b022-3b0323f00f4e
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 应为整数常量
出现 `#ExternalSource` 指令，其中第二个参数不是整数文本。 在此上下文中，仅整数文本有效。 已命名的常量或枚举成员无效。  
  
 **错误 ID：**BC30204  
  
### 更正此错误  
  
1.  使用已命名的常量或枚举成员，而非文本。  
  
2.  提供一个整数文本作为 `#ExternalSource` 指令的第二个参数。  
  
## 请参阅  
 [\#ExternalSource 指令](/dotnet/visual-basic/language-reference/directives/externalsource-directive)
---
title: "“ReadOnly”属性必须提供“Get” | Microsoft Docs"
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
  - "bc30126"
  - "vbc30126"
helpviewer_keywords: 
  - "BC30126"
ms.assetid: a522c39e-1f11-45c8-a00b-3546c842909a
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “ReadOnly”属性必须提供“Get”
如果某个属性声明为 `ReadOnly`，则它必须提供用于读取其值的过程。  
  
 **错误 ID：**BC30126  
  
### 更正此错误  
  
1.  请确保 `Property` 语句和 `End Property` 语句之间包含 `Get` 过程。  
  
2.  验证 `Property` 声明中的其他过程是否正确终止。  
  
## 请参阅  
 [Property 语句](/dotnet/visual-basic/language-reference/statements/property-statement)   
 [Get 语句](/dotnet/visual-basic/language-reference/statements/get-statement)
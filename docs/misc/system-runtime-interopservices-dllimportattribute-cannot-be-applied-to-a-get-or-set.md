---
title: "&quot;System.Runtime.InteropServices.DllImportAttribute&quot; 不能应用于 &quot;Get&quot; 或 &quot;Set&quot; | Microsoft Docs"
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
  - "vbc31524"
  - "bc31524"
helpviewer_keywords: 
  - "BC31524"
ms.assetid: 3603e33a-a80b-448d-83e0-e5dbc9af4dcf
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;System.Runtime.InteropServices.DllImportAttribute&quot; 不能应用于 &quot;Get&quot; 或 &quot;Set&quot;
向 `Get` 或 `Set` 属性过程应用了 `DllImportAttribute` 特性。  
  
 **错误 ID：**BC31524  
  
### 更正此错误  
  
1.  将 `DllImportAttribute` 从 `Get` 和 `Set` 属性过程中删除。  
  
## 请参阅  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Property 过程](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)
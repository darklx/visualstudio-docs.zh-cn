---
title: "XML 特性“attribute1”必须在 XML 特性“attribute2”之前出现 | Microsoft Docs"
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
  - "bc31157"
  - "vbc31157"
helpviewer_keywords: 
  - "BC31157"
ms.assetid: d8d8769e-533d-454e-b145-99955ce45cc5
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML 特性“attribute1”必须在 XML 特性“attribute2”之前出现
按无效顺序指定了 XML 文档文本中的特性。 XML 文档文本的有效特性顺序基于 XML 1.0 规范。 例如，XML 文档文本的 `encoding` 特性必须紧跟在 `version` 特性的后面。  
  
 **错误 ID：**BC31157  
  
### 更正此错误  
  
-   使用 XML 1.0 规范中指定的准则更新 XML 文档文本的特性顺序。  
  
## 请参阅  
 [XML 文本和 XML 1.0 规范](/dotnet/visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification)   
 [XML 文档文本](/dotnet/visual-basic/language-reference/xml-literals/xml-document-literal)   
 [XML 文本](/dotnet/visual-basic/language-reference/xml-literals/index)   
 [XML](/dotnet/visual-basic/programming-guide/language-features/xml/index)
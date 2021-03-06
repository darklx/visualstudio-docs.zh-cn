---
title: "“&lt;propertyname&gt;”的“&lt;keyword&gt;”访问器已过时（Visual Basic 警告） | Microsoft Docs"
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
  - "vbc40020"
  - "bc40020"
helpviewer_keywords: 
  - "BC40020"
ms.assetid: 005440f4-6e82-421c-b2ce-9c5139325bac
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “&lt;propertyname&gt;”的“&lt;keyword&gt;”访问器已过时（Visual Basic 警告）
语句尝试读取或写入属性，为此属性，其相应的过程已标记为 <xref:System.ObsoleteAttribute> 特性，指令会将其视为警告。  
  
 可以通过将 <xref:System.ObsoleteAttribute> 应用于任意编程元素，将其标记为不再使用。 如果执行此操作，则可以将特性的 <xref:System.ObsoleteAttribute.IsError%2A> 属性设置为 `True` 或 `False`。 如果设置为 `True`，则编译器将尝试使用该元素的操作视为错误。 如果设置为 `False`，或将其默认为 `False`，则编译器会在有操作尝试使用该元素时发出警告。  
  
 默认情况下，此消息是一个警告，因为 <xref:System.ObsoleteAttribute> 的 <xref:System.ObsoleteAttribute.IsError%2A> 属性为 `False`。 有关隐藏警告或将警告视为错误的详细信息，请参见 [在 Visual Basic 中配置警告](../ide/configuring-warnings-in-visual-basic.md)。  
  
 **错误 ID:** BC40020  
  
### 更正此错误  
  
1.  确保源代码引用正确拼写属性名称。  
  
2.  避免以生成此消息的方式（读取或写入）访问属性。  
  
## 请参阅  
 [不在生成中：Visual Basic 中使用的特性](http://msdn.microsoft.com/zh-cn/22231318-8a40-49af-9245-e0aab723563b)   
 [不在生成中：特性的应用程序](http://msdn.microsoft.com/zh-cn/2b1703ed-4437-49b3-bc0b-568094324f47)   
 [Property 过程](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)
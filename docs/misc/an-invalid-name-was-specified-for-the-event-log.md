---
title: "为事件日志指定了无效名称 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 为事件日志指定了无效名称
为事件日志指定了无效名称。 通常名称中存在无效字符、文件名太长或空白文件名会导致此结果。  
  
### 更正此错误  
  
-   如果指定的名称多于 8 个字符，请确保与其他事件日志名称之间不存在冲突。 当确定名称是否唯一时，将仅计算前八个字符。  
  
-   如果提供路径，请确保它被正确解析。  
  
-   检查此名称中是否不存在任何无效字符。 不能在文件名中使用的字符包括 `<`、`>`、`:`、`"`、`/`、`\` 和 `|`。  
  
## 请参阅  
 [如何：分析文件路径](../Topic/How%20to:%20Parse%20File%20Paths%20in%20Visual%20Basic.md)   
 [如何：重命名文件](../Topic/How%20to:%20Rename%20a%20File%20in%20Visual%20Basic.md)   
 [How to: Create and Remove Custom Event Logs](http://msdn.microsoft.com/zh-cn/af9b7da0-80c7-46ac-b7f7-897063ddd503)
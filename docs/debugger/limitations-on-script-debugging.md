---
title: "脚本调试的限制 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- ASPX breakpoint mapping, limitations
- script debugging, limitations
- breakpoint mapping, limitations
ms.assetid: 280eead5-693c-47af-967f-dfe9d23f84db
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1b254cddf7a31da0bf9f9825c256f2e94583f538
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="limitations-on-script-debugging"></a>脚本调试的限制
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 支持对客户端脚本进行调试，但受本主题中的限制约束。  
  
## <a name="limitations-on-breakpoint-mapping-with-client-side-script"></a>有关客户端脚本的断点映射的限制  
 利用 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]，您能够在服务器端 ASPX 或 HTML 文件中设置断点，该文件在运行时将转换为客户端文件。 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 将断点从服务器端文件映射到客户端文件中的相应断点，前提是遵照以下限制：  
  
-   必须在 `<script>` 块的内部设置断点。 如果断点位于内联脚本或 `<% %>` 块中，则无法进行映射。  
  
-   页的浏览器 URL 必须包含页名称。 例如，http://microsoft.com/default.apsx。 断点映射无法识别从地址（如 http://microsoft.com）到默认页的重定向。  
  
-   断点必须设置在由浏览器 URL 指定的页内，而不能设置在该页包括的 ASPX 控件 (ascx) 文件、母版页或其他文件中。 无法映射包含的页中设置的断点。  
  
-   如果将断点设置在 `<script defer=true>` 块中，将无法进行映射。  
  
-   对于 `<script id="">` 块中设置的断点，断点映射将忽略 `id` 特性。  
  
## <a name="breakpoint-mapping-and-duplicate-lines"></a>断点映射和重复行  
 为了查找服务器端脚本和客户端脚本中的对应位置，断点映射算法将逐行检查代码。 该算法假定每一行都是唯一的。 如果有两行或更多行包含相同的代码，而断点设置在其中一个重复行上，则断点映射算法可能会在客户端文件中选择错误的重复行。 若要避免这种情况，请向设置了断点的行中添加一条注释。 例如：  
  
```  
i++ ;  
i ++; // I added a comment, so this line is now unique  
i ++;  
```
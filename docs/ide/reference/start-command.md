---
title: "“启动”命令 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: debug.start
helpviewer_keywords:
- Start command
- Debug.Start command
ms.assetid: dc4e4aa2-b0ab-4e00-92db-6dc3058ddc21
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f83fbf1427951057f2154e032fb58b178c8b39fc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="start-command"></a>“启动”命令
开始调试启动项目。  
  
## <a name="syntax"></a>语法  
  
```  
Debug.Start [address]  
```  
  
## <a name="arguments"></a>参数  
 `address`  
 可选。 程序挂起执行的地址，类似于源代码中的断点。 此参数仅在调试模式下有效。  
  
## <a name="remarks"></a>备注  
 “启动”命令在执行时会对指定的地址执行 RunToCursor 操作。  
  
## <a name="example"></a>示例  
 此示例启动调试器并忽略任何发生的异常。  
  
```  
>Debug.Start  
```  
  
## <a name="see-also"></a>另请参阅  
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [“命令”窗口](../../ide/reference/command-window.md)   
 [“查找/命令”框](../../ide/find-command-box.md)   
 [Visual Studio 命令别名](../../ide/reference/visual-studio-command-aliases.md)
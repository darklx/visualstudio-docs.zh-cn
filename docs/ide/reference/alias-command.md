---
title: "“别名”命令 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: tools.alias
helpviewer_keywords:
- aliases, Visual Studio commands
- commands, aliases
- Tools.Alias command
- command aliases
- alias command
ms.assetid: bdf857df-b5d5-450f-8c10-a6fd4dccc130
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cac24838cd848770c45794637620b70cea3e1bd6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="alias-command"></a>“别名”命令
为完整命令、完整命令和参数或另一个别名创建新别名。  
  
> [!TIP]
>  键入 `>alias` 但不带任何参数会显示别名及其定义的当前列表。  
  
## <a name="syntax"></a>语法  
  
```  
Tools.Alias [/delete] [/reset] [aliasname] [aliasstring]  
```  
  
## <a name="arguments"></a>参数  
 `aliasname`  
 可选。 新别名的名称。 如果不为 `aliasname` 提供任何值，则显示当前别名及其定义的列表。  
  
 `aliasstring`  
 可选。 完整命令名称、现有别名或想创建为别名的任何参数。 如果不为 `aliasstring` 提供任何值，则显示指定别名的名称和字符串。  
  
## <a name="switches"></a>开关  
 /delete 或 /del 或 /d  
 可选。 删除指定别名，将其从自动补全中删除。  
  
 /reset  
 可选。 将预定义别名的列表重置为其原始设置。 即还原所有预定义别名，并删除所有用户定义的别名。  
  
## <a name="remarks"></a>备注  
 别名表示命令，因此别名必须位于命令行的开头。  
  
 发出此命令时，应将开关紧跟在命令（而不是别名）之后，否则开关本身会被视为别名字符串。  
  
 `/reset` 开关会在还原别名之前要求确认。 `/reset` 没有缩写形式。  
  
## <a name="examples"></a>示例  
 此示例会为完整命令 Edit.MakeUpperCase 创建一个新别名 `upper`。  
  
```  
>Tools.Alias upper Edit.MakeUpperCase  
```  
  
 此示例会删除别名 `upper`。  
  
```  
>Tools.alias /delete upper  
```  
  
 此示例会显示所有当前别名和定义的列表。  
  
```  
>Tools.Alias  
```  
  
## <a name="see-also"></a>另请参阅  
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [“命令”窗口](../../ide/reference/command-window.md)   
 [“查找/命令”框](../../ide/find-command-box.md)   
 [Visual Studio 命令别名](../../ide/reference/visual-studio-command-aliases.md)
---
title: "XmlPeek 任务 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- XmlPeek task [MSBuild]
- MSBuild, XmlPeek task
ms.assetid: 19196031-a3bc-41b5-9c4a-f2572630e179
caps.latest.revision: "4"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 7238e549011d5f80ce2c8f006f56f6bb0f2de58d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="xmlpeek-task"></a>XmlPeek 任务
从 XML 文件返回 XPath 查询指定的值。  
  
## <a name="parameters"></a>参数  
 下表描述了 `XmlPeek` 任务的参数。  
  
|参数|描述|  
|---------------|-----------------|  
|`Namespaces`|可选 `String` 参数。<br /><br /> 指定 XPath 查询前缀的命名空间。|  
|`Query`|可选 `String` 参数。<br /><br /> 指定 XPath 查询。|  
|`Result`|可选的 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 输出参数。<br /><br /> 包含由此任务返回的结果。|  
|`XmlContent`|可选 `String` 参数。<br /><br /> 指定 XML 输入为字符串。|  
|`XmlInputPath`|可选 <xref:Microsoft.Build.Framework.ITaskItem> 参数。<br /><br /> 指定 XML 输入为文件路径。|  
  
## <a name="remarks"></a>备注  
 除了具有表中列出的参数外，此任务还将从本身继承自 <xref:Microsoft.Build.Utilities.Task> 类的 <xref:Microsoft.Build.Tasks.TaskExtension> 类继承参数。 有关这些其他参数的列表及其说明的信息，请参阅 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)。  
  
## <a name="see-also"></a>另请参阅  
 [任务](../msbuild/msbuild-tasks.md)   
 [任务参考](../msbuild/msbuild-task-reference.md)
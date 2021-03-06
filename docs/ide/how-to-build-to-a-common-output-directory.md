---
title: "如何：生成到公共输出目录 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- output directory
- builds [Visual Studio], common directory
- common directory
ms.assetid: 1fcc2c48-07cb-4c4f-9556-36945e7dfc4e
caps.latest.revision: "7"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0082f69e0c35bb84a15a8dd4798e7a17b6a3dd7c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-build-to-a-common-output-directory"></a>如何：生成到公共输出目录
默认情况下，[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 将解决方案中的每个项目生成到其在解决方案中自己的文件夹中。 可以通过更改项目的生成输出路径来强制将所有输出都放到相同的文件夹中。  
  
### <a name="to-place-all-solution-outputs-in-a-common-directory"></a>将所有解决方案输出都放到一个共同目录中  
  
1.  单击解决方案中的项目。  
  
2.  在“项目”菜单上，单击“属性”。  
  
3.  根据项目的类型，单击“编译”选项卡或“生成”选项卡，并将“输出路径”设置为适用于解决方案中所有项目的文件夹。  
  
4.  为解决方案中的所有项目重复 1-3 步骤。  
  
## <a name="see-also"></a>另请参阅  
 [编译和生成](../ide/compiling-and-building-in-visual-studio.md)   
 [如何：更改生成输出目录](../ide/how-to-change-the-build-output-directory.md)
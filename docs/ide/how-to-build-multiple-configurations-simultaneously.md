---
title: "如何：同时生成多个配置 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba830937-3317-4674-8cc2-c0cd565603c5
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: eca23f38a27ac43246fd6fbf0b4449630ef3f64d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-build-multiple-configurations-simultaneously"></a>如何：同时生成多个配置
使用“批生成”对话框，可以同时使用大多数类型的项目的多个甚至所有生成配置来生成这些项目。 但是，不能同时在多个生成配置中生成以下类型的项目：  
  
1.  使用 JavaScript 为 Windows 生成的 [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] 应用。  
  
2.  所有 Visual Basic 项目。  
  
 有关生成配置的详细信息，请参阅[了解生成配置](../ide/understanding-build-configurations.md)。  
  
### <a name="to-build-a-project-in-multiple-build-configurations"></a>在多个生成配置中生成项目  
  
1.  在菜单栏上，依次选择“生成”、“批生成”。  
  
2.  在“生成”列中，选择要在其中生成项目的配置的复选框。  
  
    > [!TIP]
    >  若要编辑或创建解决方案的生成配置，请在菜单栏上选择“生成”、“配置管理器”，以打开“配置管理器”对话框。 在对解决方案的生成配置进行编辑后，请选择“批生成”对话框中的“重新生成”按钮，以更新解决方案中项目的所有生成配置。  
  
3.  选择“生成”或“重新生成”按钮以使用指定配置生成项目。  
  
## <a name="see-also"></a>另请参阅  
 [如何：创建和编辑配置](../ide/how-to-create-and-edit-configurations.md)   
 [了解生成配置](../ide/understanding-build-configurations.md)   
 [并行生成多个项目](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)
---
title: "“选项”对话框 (Visual Studio) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.toolsoptionspages
helpviewer_keywords:
- Tools Options settings
- Options dialog box
- Options dialog box, development environment
- tools [Visual Studio], customizing
ms.assetid: 02b09877-1df1-4531-a0d1-a4ca17c7f857
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b196adf16359c640ba08495b36f4ba428cf8ba48
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="options-dialog-box-visual-studio"></a>“选项”对话框 (Visual Studio)
使用“选项”对话框，可根据需要配置集成开发环境 (IDE)。 例如，可以为项目建立默认保存位置、更改 Windows 的默认外观和行为以及为常用命令创建快捷方式。 还有特定于开发语言和平台的选项。 可从“工具”菜单中访问“选项”。  
  
> [!NOTE]
>  对话框中的可用选项以及显示的菜单命令的名称和位置可能与“帮助”中的描述不同，具体取决于您的当前设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)。  
  
## <a name="layout-of-the-options-dialog-box"></a>“选项”对话框的布局  
 “选项”对话框分为两部分：左侧的导航窗格和右侧的显示区域。 导航窗格中的树控件包括文件夹节点，例如环境、文本编辑器、项目和解决方案以及源控件。 展开任意文件夹节点以列出其包含的选项页面。 为特定页面选择节点时，其选项将显示在显示区域中。  
  
 在一个 IDE 功能加载到内存之前，该功能的选项不会显示在导航窗格中。 因此，如果在结束一个会话的同时开始一个新的会话，可能不会显示之前的选项。 创建项目或运行使用特定应用程序的命令时，相关选项的节点将添加到“选项”对话框中。 只要 IDE 功能保留在内存中，这些添加的选项将保持可用。  
  
> [!NOTE]
>  某些设置集合会限定显示在“选项”对话框的导航窗格中的页面数。 可以通过选择“显示所有设置”，来选择查看所有可能的页面。  
  
## <a name="how-options-are-applied"></a>如何应用选项  
 在“选项”对话框中单击“确定”将保存所有页面上的所有设置。 单击任意页面上的“取消”将取消所有更改请求，包括刚刚在其他“选项”页面上所做的更改。 对选项设置（例如[“字体和颜色”、“环境”、“选项”对话框](../../ide/reference/fonts-and-colors-environment-options-dialog-box.md)）所做的某些更改只有在关闭并重新打开 Visual Studio 后才会生效。  
  
### <a name="show-all-settings"></a>显示所有设置  
 选择或取消选择“显示所有设置”将应用在“选项”对话框中所做的所有更改，即使尚未单击“确定”亦是如此。  
  
## <a name="see-also"></a>另请参阅  
 [自定义编辑器](../../ide/customizing-the-editor.md)
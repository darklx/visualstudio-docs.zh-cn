---
title: "结构，你的建模解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ba70ba4-2cea-4e01-93c2-055903d59470
caps.latest.revision: "14"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.openlocfilehash: aeaaa6605d316804dc49a82de72fa2c43d25b03c
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="structure-your-modeling-solution"></a>安排你的建模解决方案
若要在开发项目中有效地使用模型，团队成员必须能够同时在项目的不同部分的模型上工作。 本主题建议了一种将应用程序划分为对应整体分层关系图中层的不同部分的方案。  
  
 若要快速启动一个项目或子项目，使项目模板遵循你选择的项目结构非常有用。 本主题描述如何创建和使用此类模板。  
  
 本主题假定你正在处理一个大项目，这个项目大到需要多名团队成员，还可能有多个团队。 项目的代码和模型存储在源代码管理系统，例如 [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)]。 至少某些团队成员使用 Visual Studio 来开发模型，其他团队成员可以通过使用其他版本的 Visual Studio 来查看模型。  
  
 若要查看支持每个工具和建模功能的 Visual Studio 的版本，请参阅[体系结构和建模工具的版本支持](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)。  
  
## <a name="solution-structure"></a>解决方案结构  
 在中型或大型项目中，团队的结构以应用程序的结构为基础。 每个团队使用一种 Visual Studio 解决方案。  
  
#### <a name="to-divide-an-application-into-layers"></a>将应用程序划分为多层  
  
1.  将解决方案的结构建立在应用程序（例如，Web 应用程序、服务应用程序或桌面应用程序）的结构之上。 中讨论常见的体系结构的各种[Microsoft 应用程序体系结构指南中的应用程序原型](http://go.microsoft.com/fwlink/?LinkId=196681)。  
  
2.  创建我们称之为体系结构解决方案的 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 解决方案。 此解决方案将用于创建系统的整体设计。 它将包含模型但不包括代码。  
  
     将依赖项关系图添加到此解决方案。 依赖项关系图中，在绘制您已选择你的应用程序的体系结构。 例如，关系图可能显示以下层及相互之间的依赖关系：演示、业务逻辑和数据。  
  
4.  在体系结构依赖项关系图中创建单独的 Visual Studio 解决方案为每个层。  
  
     这些解决方案将用于开发层代码。  
  
5.  创建将表示层和共有的所有层的概念的设计的模型。 排列模型，以便可以从体系结构解决方案中看到所有模型，并从各个层中看到相关模型。  
  
     通过使用以下任一过程来实现此目的。 第一种替代方法将为每一层创建一个单独的建模项目，第二种替代方法将创建单个可在各层之间共享的建模项目。  
  
    ###### <a name="to-use-a-separate-modeling-project-for-each-layer"></a>为每个层使用单独的建模项目  
  
    1.  为每个层解决方案创建一个建模项目。  
  
         此模型将包含描述的要求和设计该层关系图。 它还可以包含显示嵌套的层的依赖项关系图。  
  
         现在，每个层都有一个模型，还有一个用于应用程序体系结构的模型。 每个解决方案都包含各自的模型。 这样使团队成员能够同时在各个层上工作。  
  
    2.  对于体系结构解决方案中，将添加每个层解决方案的建模项目。 为此，请打开体系结构解决方案。 在解决方案资源管理器，右键单击解决方案节点，指向添加，然后单击**现有项目**。 在一个层解决方案中导航到建模项目 (.modelproj)。  
  
         现在，每个模型都在这两个解决方案中可见：其“主”解决方案和体系结构解决方案。  
  
    3.  将添加到建模项目中的每个层，依赖项关系图。 开头的体系结构依赖项关系图的副本。 您可以删除不是依赖项的依赖项关系图的部分。  
  
         你还可以添加依赖项关系图表示此层的详细的结构。  
  
         这些关系图用于验证在此层中开发的代码。  
  
    4.  在体系结构解决方案中，通过使用 Visual Studio 编辑所有层的要求和设计模型。  
  
         在每个层解决方案中，引用该模型为该层开发代码。 如果你愿意将开发工作和更新模型放在不同计算机上来完成，可以使用无法创建模型的 Visual Studio 版本来阅读模型和开发代码。 你还可以在这些版本中生成模型的代码。  
  
     此方法可保证同时编辑层模型的开发人员相互之间不会干扰。  
  
     但是，由于各个模型是独立的，难以引用通用概念。 每个模型都必须有自己的元素副本，其他层和体系结构借助这些元素与相应模型产生依赖关系。 每个层中的依赖项关系图必须保持与体系结构依赖项关系图同步。 当这些元素发生更改时，很难维护同步，尽管你可以开发工具来实现这一点。  
  
    ###### <a name="to-use-a-separate-package-for-each-layer"></a>为每一层使用单独的包  
  
    1.  在每层的解决方案中，添加体系结构建模项目。 在解决方案资源管理器，右键单击解决方案节点，指向**添加**，然后单击**现有项目**。 现在从每个解决方案都可以访问这个单一建模项目：体系结构项目以及每层的开发项目。  
  
    2.  在共享的模型中，创建的每一层包： 在解决方案资源管理器，选择建模项目。 在 UML 模型资源管理器，右键单击模型根节点，指向**添加**，然后单击**包**。  
  
         每个包将包含描述的要求和设计的相应层关系图。  
  
    3.  如果需要，添加本地依赖项关系图的每个层的内部结构。  
  
     此方法允许每层的设计元素直接引用其依赖的各个层和公共体系结构的设计元素。  
  
     尽管对不同包的并发操作会导致一些冲突，但这些冲突非常易于管理，因为包存储在单独的文件中。
  
## <a name="creating-architecture-templates"></a>创建体系结构模板  
 实际操作中，你将不会同时创建所有 Visual Studio 解决方案，而是随着项目进度添加它们。 你还可能在将来的项目中使用相同的解决方案结构。  为了帮助你快速创建新的解决方案，你可以创建一个解决方案或项目模板。 可以以 Visual Studio 集成扩展 (VSIX) 格式捕捉模板，以便能够轻松地在其他计算机上分发和安装。  
  
 例如，如果你频繁使用具有演示文稿、业务和数据层的解决方案，则可以配置一个模板来创建具有这种结构的新解决方案。  
  
#### <a name="to-create-a-solution-template"></a>创建解决方案模板  
  
1.  [下载并安装导出模板向导](http://go.microsoft.com/fwlink/?LinkId=196686)，如果尚未这样做。  
  
2.  创建你想要用作将来项目的起始点的解决方案结构。  
  
3.  在“文件”  菜单上，单击“将模板导出为 VSIX” 。 **将模板导出为 VSIX 向导**打开。  
  
4.  按照该向导中的说明，选择你想要包括在模板中的项目，提供模板的名称和说明，并指定输出位置。  
  
> [!NOTE]
>  本主题中的材料取自 Visual Studio ALM Rangers 编写的“Visual Studio 体系结构工具指南”并有所改动，该指南是由最有价值的专家 (MVP)、Microsoft 服务以及 Visual Studio 产品团队和编写者合著的。 [若要下载完整的指南包，请单击此处。](http://go.microsoft.com/fwlink/?LinkID=191984)  
  
## <a name="related-materials"></a>相关材料  
 [组织和管理您的模型](http://channel9.msdn.com/posts/clinted/UML-with-VS-2010-Part-9-Organizing-and-Managing-Your-Models/)-Clint Edmondson 的视频。  
  
 [Visual Studio 体系结构工具指南](../modeling/visual-studio-architecture-tooling-guidance.md)-进一步管理团队中的模型的指南  
  
## <a name="see-also"></a>另请参阅  
 [在你的开发过程中使用模型](../modeling/use-models-in-your-development-process.md)

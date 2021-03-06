---
title: "属性的隔离舱形状 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.dsltools.dsldesigner.compartmentshape
helpviewer_keywords: Domain-Specific Language, compartment shape
ms.assetid: 9a9e112d-210d-413b-a44f-0e976a4a78bc
caps.latest.revision: "24"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 007e1a6468429212ba7d1833157a4c9a2e771652
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="properties-of-compartment-shapes"></a>分段形状的属性
隔离舱形状是一种可用于在域特定语言中显示的域类的形状。 你可以展开和折叠隔离舱。  
  
 有关详细信息，请参阅[如何定义域特定语言](../modeling/how-to-define-a-domain-specific-language.md)。 有关如何使用这些属性的详细信息，请参阅[自定义和扩展的域特定语言](../modeling/customizing-and-extending-a-domain-specific-language.md)。  
  
 隔离舱形状具有下表中列出的属性。  
  
|属性|描述|默认|  
|--------------|-----------------|-------------|  
|默认展开折叠状态|如果`Expanded`，在创建显示隔离舱。 如果`Collapsed`，它们不是。|已展开|  
|填充颜色|此形状的填充颜色。|空白|  
|填充渐变的模式|此形状填充渐变的模式。|水平|  
|Geometry|（矩形或圆角矩形） 此形状的几何图形。|矩形|  
|具有默认连接点|如果`True`、 形状将使用顶部、 底部、 左侧和正确的连接点生成的设计器中。|False|  
|是单个的隔离舱标头可见|如果`False`，且形状具有单个隔离舱的隔离舱标头不可见。|True|  
|轮廓颜色|该形状的轮廓颜色。|黑色|  
|大纲短划线样式|此形状 （实线、 短划线、 句点、 DashDot、 DashDotDot、 自定义） 大纲短划线样式。|单色|  
|轮廓粗细|该形状的轮廓粗细。|0.03125|  
|文本颜色|用于与此形状关联的文本修饰器颜色。|黑色|  
|访问修饰符|隔离舱形状的访问级别 (`public`或`internal`)。|Public|  
|自定义特性|用于将属性添加到从此隔离舱形状生成源代码类|\<无 >|  
|生成双派生|如果`True`，将生成的基本类和分部类 （以支持通过替代的自定义）。 有关详细信息，请参阅[重写和扩展生成的类](../modeling/overriding-and-extending-the-generated-classes.md)。|False|  
|具有自定义的构造函数|如果`True`，自定义的构造函数将提供的源代码中。 有关详细信息，请参阅[重写和扩展生成的类](../modeling/overriding-and-extending-the-generated-classes.md)。|False|  
|继承修饰符|介绍的从隔离舱形状生成源代码类的继承的类型 (`none`，`abstract`或`sealed`)。|无|  
|基隔离舱形状|该形状的基类。|(无)|  
|名称|该形状的名称。|当前的名称|  
|命名空间|隶属于此形状命名空间。|当前命名空间|  
|工具提示类型|如何定义工具提示 （固定的变量，或无）。 如果固定，然后的值`Fixed Tooltip Text`属性用作工具提示; 如果变量，工具提示将定义自定义代码中。|无|  
|说明|与此形状相关联的非正式说明。|\<无 >|  
|初始高度|此图形，以英寸为单位的初始高度。 对于隔离舱形状，这是仅标头部分的高度和不能调整大小。|1|  
|初始宽度|此形状，以英寸为单位的初始宽度。|1.5|  
|作为属性公开的填充颜色<br /><br /> 公开的填充渐变模式<br /><br /> 作为属性公开轮廓颜色<br /><br /> 作为属性公开大纲短划线样式<br /><br /> 公开为属性的轮廓粗细<br /><br /> 公开文本颜色|如果`True`，用户可以设置形状的规定的属性。 若要对此设置，请右击形状定义，然后单击**添加公开**。|False|  
|描述|用于记录生成的设计器。|\<无 >|  
|显示名称|将此形状的生成设计器中显示的名称。|\<无 >|  
|固定的工具提示文本|适用于固定的工具提示文本。|\<无 >|  
|帮助关键字|用于编制索引此形状的 F1 帮助关键字。|\<无 >|  
  
## <a name="see-also"></a>另请参阅  
 [域特定语言工具词汇表](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)
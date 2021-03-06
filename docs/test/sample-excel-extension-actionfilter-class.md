---
title: "示例 Excel 扩展：ActionFilter 类 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c69fe3c7-f797-4e90-b21c-f2cc4dddf152
caps.latest.revision: "11"
ms.author: douge
manager: douge
ms.openlocfilehash: 346cb9faddf2bd155c91d9fc72176020ba43197b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="sample-excel-extension-actionfilter-class"></a>示例 Excel 扩展：ActionFilter 类
此内部类扩展 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter> 类，并表示 [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] 元素上的测试操作的筛选器。  
  
## <a name="simple-properties"></a>简单属性  
 通过这些只读属性，开发人员可以指定如何通过编码的 UI 测试框架来执行此测试操作筛选器。 例如，<xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Name%2A> 属性提供操作筛选器的名称。 其他属性可获取操作筛选器的 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Category%2A>、<xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.FilterType%2A>、由此测试操作筛选器筛选的测试操作的 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Group%2A> 名称。 其他属性指示是否为 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.ApplyTimeout%2A> 以及测试操作是否为 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Enabled%2A>。  
  
## <a name="processrule-method"></a>ProcessRule 方法  
 此方法由编码的 UI 测试框架调用，并针对提供的 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack> 执行筛选器。 当堆栈中的下一个操作向单元格发送键击时，此特定重写将移除单元格的选择操作。 然后返回 `false`。  
  
## <a name="private-methods"></a>私有方法  
 `IsLeftClick` 方法确定提供的操作是否表示单击鼠标左键。 `AreActionsOnSameExcelCell` 方法确定是否针对 Excel 中同一单元格执行所提供的两个操作。  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>   
 [扩展编码的 UI 测试和操作录制以支持 Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)

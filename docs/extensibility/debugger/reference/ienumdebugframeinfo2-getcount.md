---
title: "IEnumDebugFrameInfo2::GetCount |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugFrameInfo2::GetCount
helpviewer_keywords: IEnumDebugFrameInfo2::GetCount
ms.assetid: d02a08e3-f34f-461e-8195-5157e154c481
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 895666bed2442c7b45a678525778878f7674f5d9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="ienumdebugframeinfo2getcount"></a>IEnumDebugFrameInfo2::GetCount
枚举中返回元素的数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCount(  
   ULONG* pcelt  
);  
```  
  
```csharp  
int GetCount(  
   out uint pcelt  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pcelt`  
 [out]枚举中返回元素的数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法不是指定仅通常 COM 枚举接口的一部分`Next`， `Clone`， `Skip`，和`Reset`方法需要实现。  
  
## <a name="see-also"></a>另请参阅  
 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)
---
title: "IDebugThread2::SetThreadName |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugThread2::SetThreadName
helpviewer_keywords: IDebugThread2::SetThreadName
ms.assetid: fa934121-3f58-44dc-9c30-d3f752e44c8b
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fd32ebe91a1a88da1d33bba37ae56084fc48b891
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="idebugthread2setthreadname"></a>IDebugThread2::SetThreadName
设置线程的名称。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetThreadName (   
   LPCOLESTR pszName  
);  
```  
  
```csharp  
int SetThreadName (   
   string pszName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pszName`  
 [in]线程的名称。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 若要获取线程名称，请调用[GetName](../../../extensibility/debugger/reference/idebugthread2-getname.md)方法。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [GetName](../../../extensibility/debugger/reference/idebugthread2-getname.md)
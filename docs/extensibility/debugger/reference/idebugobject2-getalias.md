---
title: "IDebugObject2::GetAlias |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugObject2::GetAlias
helpviewer_keywords: IDebugObject2::GetAlias method
ms.assetid: aa6824d5-c932-42ba-8713-950e7d1fb42f
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cdb6510edcb11df6359066637fd796d142ddae1a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="idebugobject2getalias"></a>IDebugObject2::GetAlias
如果有的话，请获取与此对象关联的别名。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetAlias(  
   IDebugAlias** ppAlias  
);  
```  
  
```csharp  
int GetAlias(  
   out IDebugAlias ppAlias  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppAlias`  
 [out]返回[IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)表示此对象的别名的对象; 否则，返回 null 值。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回，则为 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 通过调用创建对象的别名[CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md)方法。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)   
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)
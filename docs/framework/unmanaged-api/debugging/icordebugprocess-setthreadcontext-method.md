---
title: "ICorDebugProcess::SetThreadContext 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.SetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7d40d455ea17b8df2acd77a1222ac6b080116c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocesssetthreadcontext-method"></a>ICorDebugProcess::SetThreadContext 方法
在此过程中设置给定线程的上下文。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
#### <a name="parameters"></a>参数  
 `threadID`  
 [in]为其设置上下文线程的 ID。  
  
 `contextSize`  
 [in] `context` 数组的大小。  
  
 `context`  
 [in]描述线程的上下文的字节数组。  
  
 上下文指定在其执行线程的处理器的体系结构。  
  
## <a name="remarks"></a>备注  
 调试器应调用此方法，而不是 Win32`SetThreadContext`函数，因为线程实际上可能是处于"被劫持"状态，在其中其上下文已被暂时更改。 只有当线程处于本机代码时，应使用此方法。 使用[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)托管代码中的线程。 你应从不需要以在带外 (OOB) 调试事件期间修改的线程上下文。  
  
 传递的数据必须是当前平台的上下文结构。  
  
 如果使用不正确，此方法会损坏运行时。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

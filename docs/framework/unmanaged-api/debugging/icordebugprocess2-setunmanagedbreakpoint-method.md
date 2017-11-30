---
title: "ICorDebugProcess2::SetUnmanagedBreakpoint 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.SetUnmanagedBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::SetUnmanagedBreakpoint
helpviewer_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint method [.NET Framework debugging]
- SetUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 93829d15-d942-4e2d-b7a4-dfc9d7fb96be
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dd2d6ac2967b4314a57aa30bbb34ff3d354a6365
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="05c5d-102">ICorDebugProcess2::SetUnmanagedBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="05c5d-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="05c5d-103">指定的本机映像的偏移量处设置非托管的断点。</span><span class="sxs-lookup"><span data-stu-id="05c5d-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05c5d-104">语法</span><span class="sxs-lookup"><span data-stu-id="05c5d-104">Syntax</span></span>  
  
```  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]   
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="05c5d-105">参数</span><span class="sxs-lookup"><span data-stu-id="05c5d-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="05c5d-106">[in]A`CORDB_ADDRESS`对象，它指定的本机映像偏移量。</span><span class="sxs-lookup"><span data-stu-id="05c5d-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="05c5d-107">[in]大小，以字节为单位的`buffer`数组。</span><span class="sxs-lookup"><span data-stu-id="05c5d-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="05c5d-108">[out]一个数组，包含由断点替换操作码。</span><span class="sxs-lookup"><span data-stu-id="05c5d-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="05c5d-109">[out]指向返回中的字节数的指针`buffer`数组。</span><span class="sxs-lookup"><span data-stu-id="05c5d-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05c5d-110">备注</span><span class="sxs-lookup"><span data-stu-id="05c5d-110">Remarks</span></span>  
 <span data-ttu-id="05c5d-111">如果公共语言运行时 (CLR) 内的本机映像偏移量，则将忽略断点。</span><span class="sxs-lookup"><span data-stu-id="05c5d-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="05c5d-112">这样，以避免断点设置由调试器时调度带的断点，CLR。</span><span class="sxs-lookup"><span data-stu-id="05c5d-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05c5d-113">要求</span><span class="sxs-lookup"><span data-stu-id="05c5d-113">Requirements</span></span>  
 <span data-ttu-id="05c5d-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="05c5d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05c5d-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05c5d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05c5d-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05c5d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05c5d-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05c5d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
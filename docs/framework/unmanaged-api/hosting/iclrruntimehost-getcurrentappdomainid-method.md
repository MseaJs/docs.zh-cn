---
title: "ICLRRuntimeHost::GetCurrentAppDomainId 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.GetCurrentAppDomainId
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 001a467536c899c3849b5689e65bdaf404beab75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="50228-102">ICLRRuntimeHost::GetCurrentAppDomainId 方法</span><span class="sxs-lookup"><span data-stu-id="50228-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="50228-103">获取的数字标识符<xref:System.AppDomain>，当前正在执行。</span><span class="sxs-lookup"><span data-stu-id="50228-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50228-104">语法</span><span class="sxs-lookup"><span data-stu-id="50228-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="50228-105">参数</span><span class="sxs-lookup"><span data-stu-id="50228-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="50228-106">[out]数字标识符<xref:System.AppDomain>，当前正在执行。</span><span class="sxs-lookup"><span data-stu-id="50228-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50228-107">返回值</span><span class="sxs-lookup"><span data-stu-id="50228-107">Return Value</span></span>  
  
|<span data-ttu-id="50228-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50228-108">HRESULT</span></span>|<span data-ttu-id="50228-109">描述</span><span class="sxs-lookup"><span data-stu-id="50228-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50228-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="50228-110">S_OK</span></span>|<span data-ttu-id="50228-111">`GetCurrentAppDomainId`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="50228-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="50228-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="50228-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="50228-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="50228-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="50228-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="50228-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="50228-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="50228-115">The call timed out.</span></span>|  
|<span data-ttu-id="50228-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="50228-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="50228-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="50228-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="50228-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="50228-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="50228-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="50228-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="50228-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="50228-120">E_FAIL</span></span>|<span data-ttu-id="50228-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="50228-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="50228-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="50228-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="50228-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="50228-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50228-124">备注</span><span class="sxs-lookup"><span data-stu-id="50228-124">Remarks</span></span>  
 <span data-ttu-id="50228-125">`pdwAppDomainId`参数设置的值为<xref:System.AppDomain.Id%2A>属性<xref:System.AppDomain>在当前线程正在执行。</span><span class="sxs-lookup"><span data-stu-id="50228-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50228-126">要求</span><span class="sxs-lookup"><span data-stu-id="50228-126">Requirements</span></span>  
 <span data-ttu-id="50228-127">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="50228-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50228-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="50228-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50228-129">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="50228-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50228-130">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50228-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50228-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50228-131">See Also</span></span>  
 <xref:System.AppDomain>  
 <xref:System.AppDomainManager>  
 [<span data-ttu-id="50228-132">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="50228-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
---
title: CoreResponseData.m_ResponseHeaders Field
ms.date: 01/29/2018
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_ResponseHeaders
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.author: stwhi
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: eaece5bfe9cda7d35905ecd7e1da503ec11faf9c
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="coreresponsedatamresponseheaders-field"></a><span data-ttu-id="94523-102">CoreResponseData.m\_ResponseHeaders 字段</span><span class="sxs-lookup"><span data-stu-id="94523-102">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="94523-103">`CoreResponseData.m_ResponseHeaders`是<xref:System.Net.WebHeaderCollection>与服务器响应关联的标头。</span><span class="sxs-lookup"><span data-stu-id="94523-103">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="94523-104">语法</span><span class="sxs-lookup"><span data-stu-id="94523-104">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="94523-105">此 API 不是在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="94523-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="94523-106">相反，应使用<xref:System.Diagnostics.DiagnosticSource>连接网络的代码。</span><span class="sxs-lookup"><span data-stu-id="94523-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="94523-107">请参阅[DiagnosticSource 用户指南](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。</span><span class="sxs-lookup"><span data-stu-id="94523-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="94523-108">Microsoft 不支持在生产应用程序在任何情况下使用此类。</span><span class="sxs-lookup"><span data-stu-id="94523-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="94523-109">惠?</span><span class="sxs-lookup"><span data-stu-id="94523-109">Requirements</span></span>

<span data-ttu-id="94523-110">**Namespace:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="94523-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="94523-111">**程序集：**系统 （在 System.dll)</span><span class="sxs-lookup"><span data-stu-id="94523-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="94523-112">**.NET framework 版本：**自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="94523-112">**.NET Framework versions:** Available since 2.0.</span></span>
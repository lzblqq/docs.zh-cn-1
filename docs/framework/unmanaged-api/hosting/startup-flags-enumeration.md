---
title: "STARTUP_FLAGS 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: STARTUP_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: STARTUP_FLAGS
helpviewer_keywords: STARTUP_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 4f043594-0c45-4bc6-988e-a6793f0d8d06
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ebfb45e6d568b4fa1db209264e02332df636474f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="startupflags-enumeration"></a><span data-ttu-id="a7aac-102">STARTUP_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="a7aac-102">STARTUP_FLAGS Enumeration</span></span>
<span data-ttu-id="a7aac-103">包含指示公共语言运行时 (CLR) 的启动行为的值。</span><span class="sxs-lookup"><span data-stu-id="a7aac-103">Contains values that indicate the startup behavior of the common language runtime (CLR).</span></span> <span data-ttu-id="a7aac-104">默认情况下，垃圾回收是是非并发的并且只基类库加载到非特定于域的区域。</span><span class="sxs-lookup"><span data-stu-id="a7aac-104">By default, garbage collection is non-concurrent, and only the base class library is loaded into the domain-neutral area.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7aac-105">语法</span><span class="sxs-lookup"><span data-stu-id="a7aac-105">Syntax</span></span>  
  
```  
typedef enum {  
    STARTUP_CONCURRENT_GC                         = 0x1,  
    STARTUP_LOADER_OPTIMIZATION_MASK              = 0x3<<1,  
    STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN     = 0x1<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN      = 0x2<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST = 0x3<<1,  
  
    STARTUP_LOADER_SAFEMODE                       = 0x10,  
    STARTUP_LOADER_SETPREFERENCE                  = 0x100,  
  
    STARTUP_SERVER_GC                             = 0x1000,  
    STARTUP_HOARD_GC_VM                           = 0x2000,  
  
    STARTUP_SINGLE_VERSION_HOSTING_INTERFACE      = 0x4000,  
    STARTUP_LEGACY_IMPERSONATION                  = 0x10000,  
    STARTUP_DISABLE_COMMITTHREADSTACK             = 0x20000,  
    STARTUP_ALWAYSFLOW_IMPERSONATION              = 0x40000,  
    STARTUP_TRIM_GC_COMMIT                        = 0x80000,  
  
    STARTUP_ETW                                   = 0x100000,  
    STARTUP_ARM                                   = 0x400000  
} STARTUP_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="a7aac-106">成员</span><span class="sxs-lookup"><span data-stu-id="a7aac-106">Members</span></span>  
  
|<span data-ttu-id="a7aac-107">成员</span><span class="sxs-lookup"><span data-stu-id="a7aac-107">Member</span></span>|<span data-ttu-id="a7aac-108">描述</span><span class="sxs-lookup"><span data-stu-id="a7aac-108">Description</span></span>|  
|------------|-----------------|  
|`STARTUP_CONCURRENT_GC`|<span data-ttu-id="a7aac-109">指定应使用并发垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="a7aac-109">Specifies that concurrent garbage collection should be used.</span></span> <span data-ttu-id="a7aac-110">如果在单处理器计算机上，调用方要求提供服务器版本和并发垃圾回收，工作站版本和非并发垃圾回收是改为运行。</span><span class="sxs-lookup"><span data-stu-id="a7aac-110">If the caller asks for the server build and concurrent garbage collection on a single-processor machine, the workstation build and non-concurrent garbage collection are run instead.</span></span> <span data-ttu-id="a7aac-111">**注意：**运行 WOW64 的应用程序中不支持并发垃圾回收 x86 仿真程序上实现 （以前称为 ia-64） 的 Intel 的 Itanium 体系结构的 64 位系统。</span><span class="sxs-lookup"><span data-stu-id="a7aac-111">**Note:**  Concurrent garbage collection is not supported in applications that are running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="a7aac-112">有关使用 64 位 Windows 系统上的 WOW64 的详细信息，请参阅[运行 32 位应用程序](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a7aac-112">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx).</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MASK`|<span data-ttu-id="a7aac-113">指定应发生的加载程序优化。</span><span class="sxs-lookup"><span data-stu-id="a7aac-113">Specifies that loader optimization shall occur.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`|<span data-ttu-id="a7aac-114">不指定的任何程序集加载为非特定于域的。</span><span class="sxs-lookup"><span data-stu-id="a7aac-114">Specifies that no assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`|<span data-ttu-id="a7aac-115">指定的所有程序集加载为非特定于域的。</span><span class="sxs-lookup"><span data-stu-id="a7aac-115">Specifies that all assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`|<span data-ttu-id="a7aac-116">指定所有具有强名称程序集将作为非特定于域的加载。</span><span class="sxs-lookup"><span data-stu-id="a7aac-116">Specifies that all strong-named assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_SAFEMODE`|<span data-ttu-id="a7aac-117">指定 CLR 版本策略将不应用于中传递的版本。</span><span class="sxs-lookup"><span data-stu-id="a7aac-117">Specifies that CLR version policy will not be applied to the version passed in.</span></span> <span data-ttu-id="a7aac-118">将加载指定的 CLR 的确切版本。</span><span class="sxs-lookup"><span data-stu-id="a7aac-118">The exact version specified of the CLR will be loaded.</span></span> <span data-ttu-id="a7aac-119">填充码不评估策略，以确定最新的兼容版本。</span><span class="sxs-lookup"><span data-stu-id="a7aac-119">The shim does not evaluate policy to determine the latest compatible version.</span></span>|  
|`STARTUP_LOADER_SETPREFERENCE`|<span data-ttu-id="a7aac-120">指定将设置，但不是实际启动首选的运行时。</span><span class="sxs-lookup"><span data-stu-id="a7aac-120">Specifies that the preferred runtime will be set, but not actually started.</span></span>|  
|`STARTUP_SERVER_GC`|<span data-ttu-id="a7aac-121">指定将使用服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="a7aac-121">Specifies that the server garbage collection will be used.</span></span>|  
|`STARTUP_HOARD_GC_VM`|<span data-ttu-id="a7aac-122">指定垃圾回收将使用的虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="a7aac-122">Specifies that garbage collection will keep the virtual address used.</span></span>|  
|`STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`|<span data-ttu-id="a7aac-123">指定，将不会允许混合使用托管接口。</span><span class="sxs-lookup"><span data-stu-id="a7aac-123">Specifies that mixing a hosting interface will not be allowed.</span></span>|  
|`STARTUP_LEGACY_IMPERSONATION`|<span data-ttu-id="a7aac-124">指定的模拟不应流经异步点默认情况下。</span><span class="sxs-lookup"><span data-stu-id="a7aac-124">Specifies that impersonation should not flow across asynchronous points by default.</span></span>|  
|`STARTUP_DISABLE_COMMITTHREADSTACK`|<span data-ttu-id="a7aac-125">指定当线程开始运行时不应提交完整的线程堆栈。</span><span class="sxs-lookup"><span data-stu-id="a7aac-125">Specifies that the full thread stack should not be committed when the thread starts running.</span></span>|  
|`STARTUP_ALWAYSFLOW_IMPERSONATION`|<span data-ttu-id="a7aac-126">指定托管的模拟和实现通过平台调用将流经异步点。</span><span class="sxs-lookup"><span data-stu-id="a7aac-126">Specifies that managed impersonations and impersonations achieved through platform invoke will flow across asynchronous points.</span></span> <span data-ttu-id="a7aac-127">默认情况下，只有托管的模拟将流经异步点。</span><span class="sxs-lookup"><span data-stu-id="a7aac-127">By default, only managed impersonations will flow across asynchronous points.</span></span>|  
|`STARTUP_TRIM_GC_COMMIT`|<span data-ttu-id="a7aac-128">指定当系统内存不足时，垃圾回收将使用较少的提交的空间。</span><span class="sxs-lookup"><span data-stu-id="a7aac-128">Specifies that garbage collection will use less committed space when system memory is low.</span></span> <span data-ttu-id="a7aac-129">请参阅`gcTrimCommitOnLowMemory`中[针对共享的 Web 承载优化](../../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)。</span><span class="sxs-lookup"><span data-stu-id="a7aac-129">See `gcTrimCommitOnLowMemory` in [Optimization for Shared Web Hosting](../../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md).</span></span>|  
|`STARTUP_ETW`|<span data-ttu-id="a7aac-130">指定为公共语言运行时事件启用了事件跟踪 Windows (ETW)。</span><span class="sxs-lookup"><span data-stu-id="a7aac-130">Specifies that event tracing for Windows (ETW) is enabled for common language runtime events.</span></span> <span data-ttu-id="a7aac-131">从 Windows Vista 开始，事件跟踪始终会启用，因此此标志没有任何效果。</span><span class="sxs-lookup"><span data-stu-id="a7aac-131">Beginning with Windows Vista, event tracing is always enabled, so this flag has no effect.</span></span> <span data-ttu-id="a7aac-132">请参阅[控制.NET Framework 日志记录](../../../../docs/framework/performance/controlling-logging.md)。</span><span class="sxs-lookup"><span data-stu-id="a7aac-132">See [Controlling .NET Framework Logging](../../../../docs/framework/performance/controlling-logging.md).</span></span>|  
|`STARTUP_ARM`|<span data-ttu-id="a7aac-133">指定启用了应用程序域资源监视。</span><span class="sxs-lookup"><span data-stu-id="a7aac-133">Specifies that application domain resource monitoring is enabled.</span></span> <span data-ttu-id="a7aac-134">请参阅<xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>属性和[ \<appDomainResourceMonitoring > 元素](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)。</span><span class="sxs-lookup"><span data-stu-id="a7aac-134">See the <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> property and [\<appDomainResourceMonitoring> Element](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7aac-135">要求</span><span class="sxs-lookup"><span data-stu-id="a7aac-135">Requirements</span></span>  
 <span data-ttu-id="a7aac-136">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a7aac-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7aac-137">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a7aac-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7aac-138">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7aac-138">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7aac-139">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7aac-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7aac-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7aac-140">See Also</span></span>  
 [<span data-ttu-id="a7aac-141">承载枚举</span><span class="sxs-lookup"><span data-stu-id="a7aac-141">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
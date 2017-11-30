---
title: "CreateAssemblyEnum 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: CreateAssemblyEnum
helpviewer_keywords: CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c229496a79b146b5dcac3d06fa3efd9237e39d3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="5b40a-102">CreateAssemblyEnum 函数</span><span class="sxs-lookup"><span data-stu-id="5b40a-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="5b40a-103">获取一个指向[IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)可以枚举中具有指定的程序集的对象的实例[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="5b40a-103">Gets a pointer to an [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b40a-104">语法</span><span class="sxs-lookup"><span data-stu-id="5b40a-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5b40a-105">参数</span><span class="sxs-lookup"><span data-stu-id="5b40a-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="5b40a-106">[out]指向包含请求的内存位置`IAssemblyEnum`指针。</span><span class="sxs-lookup"><span data-stu-id="5b40a-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="5b40a-107">[in]留待将来扩展。</span><span class="sxs-lookup"><span data-stu-id="5b40a-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="5b40a-108">`pUnkReserved`必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="5b40a-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="5b40a-109">[in]`IAssemblyName`的请求的程序集。</span><span class="sxs-lookup"><span data-stu-id="5b40a-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="5b40a-110">此名称用于筛选在枚举。</span><span class="sxs-lookup"><span data-stu-id="5b40a-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="5b40a-111">它可以为 null 来枚举全局程序集缓存中的所有程序集。</span><span class="sxs-lookup"><span data-stu-id="5b40a-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="5b40a-112">[in]修改枚举器的行为的标志。</span><span class="sxs-lookup"><span data-stu-id="5b40a-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="5b40a-113">此参数将包含一位完全从[ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="5b40a-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="5b40a-114">[in]留待将来扩展。</span><span class="sxs-lookup"><span data-stu-id="5b40a-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="5b40a-115">`pvReserved`必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="5b40a-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b40a-116">备注</span><span class="sxs-lookup"><span data-stu-id="5b40a-116">Remarks</span></span>  
 <span data-ttu-id="5b40a-117">`dwFlags`参数包含一位完全从`ASM_CACHE_FLAGS`枚举。</span><span class="sxs-lookup"><span data-stu-id="5b40a-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b40a-118">要求</span><span class="sxs-lookup"><span data-stu-id="5b40a-118">Requirements</span></span>  
 <span data-ttu-id="5b40a-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5b40a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b40a-120">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="5b40a-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5b40a-121">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5b40a-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5b40a-122">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b40a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b40a-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b40a-123">See Also</span></span>  
 [<span data-ttu-id="5b40a-124">IAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="5b40a-124">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 [<span data-ttu-id="5b40a-125">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="5b40a-125">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="5b40a-126">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="5b40a-126">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
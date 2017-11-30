---
title: "ICorDebugCode3::GetReturnValueLiveOffset 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugCode3.GetReturnValueLiveOffset
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4516f2244b72bd4f254c5090b09d6d90579f1ae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a><span data-ttu-id="6ecf9-102">ICorDebugCode3::GetReturnValueLiveOffset 方法</span><span class="sxs-lookup"><span data-stu-id="6ecf9-102">ICorDebugCode3::GetReturnValueLiveOffset Method</span></span>
<span data-ttu-id="6ecf9-103">对于指定的 IL 偏移量，获取本机偏移量，以便调试器可以获取返回值从函数应放置断点。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-103">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ecf9-104">语法</span><span class="sxs-lookup"><span data-stu-id="6ecf9-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,   
    [out] ULONG32 *pFetched,   
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ecf9-105">参数</span><span class="sxs-lookup"><span data-stu-id="6ecf9-105">Parameters</span></span>  
 `ILoffset`  
 <span data-ttu-id="6ecf9-106">IL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-106">The IL offset.</span></span> <span data-ttu-id="6ecf9-107">它必须是函数调用站点，否则函数调用将失败。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-107">It must be a function call site or the function call will fail.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="6ecf9-108">可用于存储的字节数`pOffsets`。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-108">The number of bytes available to store `pOffsets`.</span></span>  
  
 `pFetched`  
 <span data-ttu-id="6ecf9-109">指向的实际返回的偏移量数的指针。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-109">A pointer to the number of offsets actually returned.</span></span> <span data-ttu-id="6ecf9-110">通常情况下，其值为 1，但单个 IL 指令可以映射到多个`CALL`程序集指令。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-110">Usually, its value is 1, but a single IL instruction can map to multiple `CALL` assembly instructions.</span></span>  
  
 `pOffsets`  
 <span data-ttu-id="6ecf9-111">本机偏移量的数组。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-111">An array of native offsets.</span></span> <span data-ttu-id="6ecf9-112">通常情况下，`pOffsets`尽管单个 IL 指令可以映射到多个映射到多个包含同一偏移量，`CALL`程序集指令。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-112">Typically, `pOffsets` contains a single offset, although a single IL instruction can map to multiple map to multiple `CALL` assembly instructions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ecf9-113">备注</span><span class="sxs-lookup"><span data-stu-id="6ecf9-113">Remarks</span></span>  
 <span data-ttu-id="6ecf9-114">此方法使用连同[icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)方法以获取返回引用类型的方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-114">This method is used along with the [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value of a method that returns a reference type.</span></span> <span data-ttu-id="6ecf9-115">传递 IL 偏移量到函数调用站点到此方法返回一个或多个本机偏移量。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-115">Passing an IL offset to a function call site to this method returns one or more native offsets.</span></span> <span data-ttu-id="6ecf9-116">调试器然后可以在这些函数中的本机偏移量上设置断点。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-116">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="6ecf9-117">当调试器遇到的其中一个断点时，你就可以将相同的 IL 偏移量传递给此方法传递[icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)方法以获取返回值。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-117">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to the [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value.</span></span> <span data-ttu-id="6ecf9-118">调试器然后应清除它所设置的所有断点。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-118">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="6ecf9-119">`ICorDebugCode3::GetReturnValueLiveOffset`和[icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)方法，你可以获取仅适用于引用类型的返回值信息。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-119">The `ICorDebugCode3::GetReturnValueLiveOffset` and [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="6ecf9-120">从值类型检索返回值信息 (即，派生自的所有类型<xref:System.ValueType>) 不支持。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-120">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="6ecf9-121">该函数将返回`HRESULT`下表中所示的值。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-121">The function returns the `HRESULT` values shown in the following table.</span></span>  
  
|<span data-ttu-id="6ecf9-122">`HRESULT` 值</span><span class="sxs-lookup"><span data-stu-id="6ecf9-122">`HRESULT` value</span></span>|<span data-ttu-id="6ecf9-123">描述</span><span class="sxs-lookup"><span data-stu-id="6ecf9-123">Description</span></span>|  
|---------------------|-----------------|  
|`S_OK`|<span data-ttu-id="6ecf9-124">成功。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-124">Success.</span></span>|  
|`CORDBG_E_INVALID_OPCODE`|<span data-ttu-id="6ecf9-125">给定的 IL 偏移量的站点不是调用指令，或该函数将返回`void`。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-125">The given IL offset site is not a call instruction, or the function returns `void`.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="6ecf9-126">给定的 IL 偏移量是正确的调用，但返回类型不支持获取返回值。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-126">The given IL offset is a proper call, but the return type is unsupported for getting a return value.</span></span>|  
  
 <span data-ttu-id="6ecf9-127">`ICorDebugCode3::GetReturnValueLiveOffset`方法是仅适用于基于 x86 和 AMD64 系统。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-127">The `ICorDebugCode3::GetReturnValueLiveOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ecf9-128">要求</span><span class="sxs-lookup"><span data-stu-id="6ecf9-128">Requirements</span></span>  
 <span data-ttu-id="6ecf9-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6ecf9-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ecf9-130">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ecf9-130">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ecf9-131">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ecf9-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ecf9-132">**.NET framework 版本：**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ecf9-132">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ecf9-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ecf9-133">See Also</span></span>  
 [<span data-ttu-id="6ecf9-134">GetReturnValueForILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="6ecf9-134">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)  
 [<span data-ttu-id="6ecf9-135">ICorDebugCode3 接口</span><span class="sxs-lookup"><span data-stu-id="6ecf9-135">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
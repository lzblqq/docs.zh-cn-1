---
title: "ICorDebugVariableHome::GetArgumentIndex 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetArgumentIndex
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentiIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 175e45758d26d8168279c825d41ee58d049edf0b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="ae9a2-102">ICorDebugVariableHome::GetArgumentIndex 方法</span><span class="sxs-lookup"><span data-stu-id="ae9a2-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>
<span data-ttu-id="ae9a2-103">获取函数自变量的索引。</span><span class="sxs-lookup"><span data-stu-id="ae9a2-103">Gets the index of a function argument.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae9a2-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae9a2-104">Syntax</span></span>  
  
```  
HRESULT GetArgumentIndex(  
    [out] ULONG32* pArgumentIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae9a2-105">参数</span><span class="sxs-lookup"><span data-stu-id="ae9a2-105">Parameters</span></span>  
 `pArgumentIndex`  
 <span data-ttu-id="ae9a2-106">[out]指向自变量索引的指针。</span><span class="sxs-lookup"><span data-stu-id="ae9a2-106">[out] A pointer to the argument index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae9a2-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ae9a2-107">Return Value</span></span>  
 <span data-ttu-id="ae9a2-108">该方法返回以下值。</span><span class="sxs-lookup"><span data-stu-id="ae9a2-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="ae9a2-109">值</span><span class="sxs-lookup"><span data-stu-id="ae9a2-109">Value</span></span>|<span data-ttu-id="ae9a2-110">描述</span><span class="sxs-lookup"><span data-stu-id="ae9a2-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="ae9a2-111">方法调用返回一个有效的自变量的索引。</span><span class="sxs-lookup"><span data-stu-id="ae9a2-111">The method call returned a valid argument index.</span></span>|  
|`E_FAIL`|<span data-ttu-id="ae9a2-112">当前[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)实例表示的本地变量。</span><span class="sxs-lookup"><span data-stu-id="ae9a2-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae9a2-113">备注</span><span class="sxs-lookup"><span data-stu-id="ae9a2-113">Remarks</span></span>  
 <span data-ttu-id="ae9a2-114">参数索引可以用于检索为此参数的元数据。</span><span class="sxs-lookup"><span data-stu-id="ae9a2-114">The argument index can be used to retrieve metadata for this argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae9a2-115">要求</span><span class="sxs-lookup"><span data-stu-id="ae9a2-115">Requirements</span></span>  
 <span data-ttu-id="ae9a2-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae9a2-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae9a2-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae9a2-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae9a2-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae9a2-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae9a2-119">**.NET framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae9a2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae9a2-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae9a2-120">See Also</span></span>  
 [<span data-ttu-id="ae9a2-121">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="ae9a2-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
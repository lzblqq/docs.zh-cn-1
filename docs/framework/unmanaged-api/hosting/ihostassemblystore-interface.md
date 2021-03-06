---
title: "IHostAssemblyStore 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore
helpviewer_keywords:
- IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c795d4baa3030817299f23c3dadf4caf7a5edc5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblystore-interface"></a>IHostAssemblyStore 接口
提供使主机可在加载程序集和模块独立于公共语言运行时 (CLR) 的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[ProvideAssembly 方法](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|获取未被引用程序集的引用[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)从调用返回[ihostassemblymanager:: Getnonhoststoreassemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)。|  
|[ProvideModule 方法](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|解析程序集或链接的 （不使用嵌入） 资源文件内的模块。|  
  
## <a name="remarks"></a>备注  
 `IHostAssemblyStore`提供的主机以加载程序集有效地基于程序集标识的方法。 主机加载程序集通过返回`IStream`直接指向字节的实例。  
  
 CLR 确定主机是否具有实现`IHostAssemblyStore`通过调用`IHostAssemblyManager::GetNonHostAssemblyStores`在初始化时。 这样主机，例如，若要控制对用户程序集的绑定，但依赖于要将绑定到.NET Framework 程序集的运行时。  
  
> [!NOTE]
>  在提供的实现`IHostAssemblyStore`，主机指定其试图解决未被引用的所有程序集`ICLRAssemblyReferenceList`从返回`IHostAssemblyManager::GetNonHostStoreAssemblies`。  
  
> [!NOTE]
>  .NET Framework 2.0 版不提供主机加载本机映像程序集的一种方法，因为由提供[本机映像生成器 (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)实用程序。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRAssemblyReferenceList 接口](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

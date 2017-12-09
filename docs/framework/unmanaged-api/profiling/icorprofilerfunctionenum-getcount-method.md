---
title: "Método ICorProfilerFunctionEnum::GetCount"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionEnum.GetCount Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionEnum::GetCount
helpviewer_keywords:
- ICorProfilerFunctionEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 62ec65e3-3e9d-400b-ae61-d24b8963995b
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 55fff79bc68f1e2b790cf93afbce6a9f6cfd3c51
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="33fd1-102">Método ICorProfilerFunctionEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="33fd1-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="33fd1-103">Obtém o número de funções que foram carregados pelo aplicativo ou à força pelo criador de perfil.</span><span class="sxs-lookup"><span data-stu-id="33fd1-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33fd1-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="33fd1-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="33fd1-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="33fd1-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="33fd1-106">[out] O número de funções que foram carregados.</span><span class="sxs-lookup"><span data-stu-id="33fd1-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33fd1-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33fd1-107">Requirements</span></span>  
 <span data-ttu-id="33fd1-108">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33fd1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33fd1-109">**Cabeçalho:** Corprof. idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="33fd1-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="33fd1-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33fd1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33fd1-111">**Versões do .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33fd1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33fd1-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="33fd1-112">See Also</span></span>  
 [<span data-ttu-id="33fd1-113">Interface ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="33fd1-113">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="33fd1-114">Interfaces de criação de perfil</span><span class="sxs-lookup"><span data-stu-id="33fd1-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
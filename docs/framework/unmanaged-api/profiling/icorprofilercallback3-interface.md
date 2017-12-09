---
title: Interface ICorProfilerCallback3
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback3
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback3
helpviewer_keywords: ICorProfilerCallback3 interface [.NET Framework profiling]
ms.assetid: be83af41-3dec-4c77-8529-9dd6b8042af6
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c62dfb9b44999309ab2be7dfdcdfba3bb5dde29c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback3-interface"></a><span data-ttu-id="7bbd5-102">Interface ICorProfilerCallback3</span><span class="sxs-lookup"><span data-stu-id="7bbd5-102">ICorProfilerCallback3 Interface</span></span>
<span data-ttu-id="7bbd5-103">Fornece métodos de retorno de chamada que o common language runtime (CLR) usa para se comunicar anexar e desanexar informações de estado para o criador de perfil.</span><span class="sxs-lookup"><span data-stu-id="7bbd5-103">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7bbd5-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="7bbd5-104">Methods</span></span>  
  
|<span data-ttu-id="7bbd5-105">Método</span><span class="sxs-lookup"><span data-stu-id="7bbd5-105">Method</span></span>|<span data-ttu-id="7bbd5-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="7bbd5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7bbd5-107">Método InitializeForAttach</span><span class="sxs-lookup"><span data-stu-id="7bbd5-107">InitializeForAttach Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md)|<span data-ttu-id="7bbd5-108">Chamado pelo CLR para que o criador de perfil que tenha a oportunidade para inicializar o estado após uma operação de anexação.</span><span class="sxs-lookup"><span data-stu-id="7bbd5-108">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span></span>|  
|[<span data-ttu-id="7bbd5-109">Método ProfilerAttachComplete</span><span class="sxs-lookup"><span data-stu-id="7bbd5-109">ProfilerAttachComplete Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerattachcomplete-method.md)|<span data-ttu-id="7bbd5-110">Chamado pelo CLR para indicar que o criador de perfil agora pode chamar os métodos de recuperação do atraso.</span><span class="sxs-lookup"><span data-stu-id="7bbd5-110">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span></span>|  
|[<span data-ttu-id="7bbd5-111">Método ProfilerDetachSucceeded</span><span class="sxs-lookup"><span data-stu-id="7bbd5-111">ProfilerDetachSucceeded Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerdetachsucceeded-method.md)|<span data-ttu-id="7bbd5-112">Notifica o criador de perfil que o common language runtime (CLR) está prestes a Descarregue o DLL do criador de perfil.</span><span class="sxs-lookup"><span data-stu-id="7bbd5-112">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7bbd5-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="7bbd5-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bbd5-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7bbd5-114">Requirements</span></span>  
 <span data-ttu-id="7bbd5-115">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bbd5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bbd5-116">**Cabeçalho:** Corprof. idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7bbd5-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7bbd5-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7bbd5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7bbd5-118">**Versões do .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bbd5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bbd5-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7bbd5-119">See Also</span></span>  
 [<span data-ttu-id="7bbd5-120">Interfaces de criação de perfil</span><span class="sxs-lookup"><span data-stu-id="7bbd5-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="7bbd5-121">Interface ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="7bbd5-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="7bbd5-122">Interface ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="7bbd5-122">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [<span data-ttu-id="7bbd5-123">Interface ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="7bbd5-123">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
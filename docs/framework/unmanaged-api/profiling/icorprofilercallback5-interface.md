---
title: Interface ICorProfilerCallback5
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback5
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback5
helpviewer_keywords: ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1a862707dc64efbf3a9b1604a0e6a4ff1be81b43
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="eaf83-102">Interface ICorProfilerCallback5</span><span class="sxs-lookup"><span data-stu-id="eaf83-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="eaf83-103">Complementa as informações para ajudar a identificar o encerramento completo de objetos ao vivo, quando usado com um um criador de perfil de [: Rootreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) ou [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)método junto com o [: Objectreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) e [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) métodos.</span><span class="sxs-lookup"><span data-stu-id="eaf83-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 <span data-ttu-id="eaf83-104">O `ICorProfilerCallback5` deve ser implementado por um criador de perfil de memória gerenciada para assinar as notificações relacionadas aos identificadores dependentes.</span><span class="sxs-lookup"><span data-stu-id="eaf83-104">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eaf83-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="eaf83-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eaf83-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="eaf83-106">Methods</span></span>  
  
|<span data-ttu-id="eaf83-107">Método</span><span class="sxs-lookup"><span data-stu-id="eaf83-107">Method</span></span>|<span data-ttu-id="eaf83-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="eaf83-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eaf83-109">Método ConditionalWeakTableElementReferences</span><span class="sxs-lookup"><span data-stu-id="eaf83-109">ConditionalWeakTableElementReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="eaf83-110">Identifica o fechamento transitivo de objetos referenciados por estas raízes por meio de referências diretas do campo de membro e de dependências `ConditionalWeakTable`.</span><span class="sxs-lookup"><span data-stu-id="eaf83-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eaf83-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eaf83-111">Requirements</span></span>  
 <span data-ttu-id="eaf83-112">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eaf83-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaf83-113">**Cabeçalho:** Corprof. idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eaf83-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eaf83-114">**Versões do .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaf83-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaf83-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="eaf83-115">See Also</span></span>  
 [<span data-ttu-id="eaf83-116">Interfaces de criação de perfil</span><span class="sxs-lookup"><span data-stu-id="eaf83-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="eaf83-117">Interface ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="eaf83-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
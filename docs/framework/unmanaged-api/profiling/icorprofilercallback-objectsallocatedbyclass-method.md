---
title: "Método ICorProfilerCallback::ObjectsAllocatedByClass"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ObjectsAllocatedByClass
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 28c0ff537a5b2133bdeb1db8aeadf5545d8dfd0f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="9e025-102">Método ICorProfilerCallback::ObjectsAllocatedByClass</span><span class="sxs-lookup"><span data-stu-id="9e025-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="9e025-103">Notifica o criador de perfil sobre o número de instâncias de cada classe especificada que foram criados desde a coleta de lixo mais recente.</span><span class="sxs-lookup"><span data-stu-id="9e025-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e025-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9e025-104">Syntax</span></span>  
  
```  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9e025-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9e025-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="9e025-106">[in] O tamanho do `classIds` e `cObjects` matrizes.</span><span class="sxs-lookup"><span data-stu-id="9e025-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="9e025-107">[in] Uma matriz de IDs, onde cada ID Especifica uma classe com uma ou mais instâncias de classe.</span><span class="sxs-lookup"><span data-stu-id="9e025-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="9e025-108">[in] Uma matriz de inteiros, onde cada inteiro Especifica o número de instâncias da classe correspondente na `classIds` matriz.</span><span class="sxs-lookup"><span data-stu-id="9e025-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e025-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="9e025-109">Remarks</span></span>  
 <span data-ttu-id="9e025-110">O `classIds` e `cObjects` as matrizes são matrizes paralelos.</span><span class="sxs-lookup"><span data-stu-id="9e025-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="9e025-111">Por exemplo, `classIds[i]` e `cObjects[i]` a mesma classe de referência.</span><span class="sxs-lookup"><span data-stu-id="9e025-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="9e025-112">Se nenhuma instância de uma classe tiver sido criada desde a coleta de lixo anterior, a classe é omitida.</span><span class="sxs-lookup"><span data-stu-id="9e025-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="9e025-113">O `ObjectsAllocatedByClass` retorno de chamada não relatarão objetos alocados no heap de objeto grande.</span><span class="sxs-lookup"><span data-stu-id="9e025-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="9e025-114">Os números relatados pelo `ObjectsAllocatedByClass` são apenas estimativas.</span><span class="sxs-lookup"><span data-stu-id="9e025-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="9e025-115">Para contagens exatas, use [: ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="9e025-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="9e025-116">O `classIds` matriz pode conter uma ou mais entradas nulas se correspondente `cObjects` matriz tem tipos estão descarregando.</span><span class="sxs-lookup"><span data-stu-id="9e025-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e025-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9e025-117">Requirements</span></span>  
 <span data-ttu-id="9e025-118">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e025-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e025-119">**Cabeçalho:** Corprof. idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9e025-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9e025-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e025-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e025-121">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e025-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e025-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9e025-122">See Also</span></span>  
 [<span data-ttu-id="9e025-123">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="9e025-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
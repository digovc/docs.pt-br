---
title: Estrutura COR_PRF_EX_CLAUSE_INFO
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_EX_CLAUSE_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_EX_CLAUSE_INFO
helpviewer_keywords: COR_PRF_EX_CLAUSE_INFO structure [.NET Framework profiling]
ms.assetid: 7d0d6fb7-bc9d-40f0-8163-c0d162eaba7d
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9952ea1d8c806c9d3ac5357d933092fb82351484
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="corprfexclauseinfo-structure"></a><span data-ttu-id="3f92e-102">Estrutura COR_PRF_EX_CLAUSE_INFO</span><span class="sxs-lookup"><span data-stu-id="3f92e-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>
<span data-ttu-id="3f92e-103">Armazena informações sobre uma instância de cláusula de exceção específica e seu quadro associado.</span><span class="sxs-lookup"><span data-stu-id="3f92e-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f92e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3f92e-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="3f92e-105">Membros</span><span class="sxs-lookup"><span data-stu-id="3f92e-105">Members</span></span>  
  
|<span data-ttu-id="3f92e-106">Membro</span><span class="sxs-lookup"><span data-stu-id="3f92e-106">Member</span></span>|<span data-ttu-id="3f92e-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="3f92e-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="3f92e-108">Um valor de [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeração que especifica o tipo de cláusula exceção o código que acabou de inserir ou à esquerda.</span><span class="sxs-lookup"><span data-stu-id="3f92e-108">A value of the [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="3f92e-109">O ponto de entrada nativo do manipulador de cláusula — por exemplo, o conteúdo do registro X86 EIP.</span><span class="sxs-lookup"><span data-stu-id="3f92e-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="3f92e-110">O ponteiro para o quadro lógico para o manipulador de cláusula — por exemplo, o conteúdo do registro X86 EBP.</span><span class="sxs-lookup"><span data-stu-id="3f92e-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="3f92e-111">O ponteiro para a pilha de sombra.</span><span class="sxs-lookup"><span data-stu-id="3f92e-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="3f92e-112">Esse valor é o conteúdo do registro BSP e só se aplica a IA64.</span><span class="sxs-lookup"><span data-stu-id="3f92e-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f92e-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="3f92e-113">Remarks</span></span>  
 <span data-ttu-id="3f92e-114">Quando uma notificação de exceção é recebida, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) pode ser usado para obter as informações de endereço e o quadro nativo para a cláusula de exceção (`catch` / `finally`/filtro) que está prestes a ser executado ou executado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3f92e-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="3f92e-115">Esses retornos de chamada do common language runtime (CLR) envolve a execução de uma cláusula de exceção:</span><span class="sxs-lookup"><span data-stu-id="3f92e-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
-   [<span data-ttu-id="3f92e-116">: Exceptioncatcherenter</span><span class="sxs-lookup"><span data-stu-id="3f92e-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)  
  
-   [<span data-ttu-id="3f92e-117">: Exceptionunwindfinallyenter</span><span class="sxs-lookup"><span data-stu-id="3f92e-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
-   [<span data-ttu-id="3f92e-118">: Exceptionsearchfilterenter</span><span class="sxs-lookup"><span data-stu-id="3f92e-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
-   [<span data-ttu-id="3f92e-119">Exceptioncatcherleave</span><span class="sxs-lookup"><span data-stu-id="3f92e-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)  
  
-   [<span data-ttu-id="3f92e-120">Exceptionunwindfinallyleave</span><span class="sxs-lookup"><span data-stu-id="3f92e-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
-   [<span data-ttu-id="3f92e-121">: Exceptionsearchfilterleave</span><span class="sxs-lookup"><span data-stu-id="3f92e-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="3f92e-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f92e-122">Requirements</span></span>  
 <span data-ttu-id="3f92e-123">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f92e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f92e-124">**Cabeçalho:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="3f92e-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="3f92e-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f92e-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f92e-126">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f92e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f92e-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3f92e-127">See Also</span></span>  
 [<span data-ttu-id="3f92e-128">Estruturas de criação de perfil</span><span class="sxs-lookup"><span data-stu-id="3f92e-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
---
title: Estrutura COR_GC_THREAD_STATS
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_THREAD_STATS
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_GC_THREAD_STATS
helpviewer_keywords: COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 10366d183ed7fd7386609e4c5726df0cea4e29a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="corgcthreadstats-structure"></a><span data-ttu-id="e8139-102">Estrutura COR_GC_THREAD_STATS</span><span class="sxs-lookup"><span data-stu-id="e8139-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="e8139-103">Contém estatísticas por thread pertencentes à coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="e8139-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8139-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e8139-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="e8139-105">Membros</span><span class="sxs-lookup"><span data-stu-id="e8139-105">Members</span></span>  
  
|<span data-ttu-id="e8139-106">Membro</span><span class="sxs-lookup"><span data-stu-id="e8139-106">Member</span></span>|<span data-ttu-id="e8139-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="e8139-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="e8139-108">O número de bytes de memória alocada no thread que está associado com a atual `COR_GC_THREAD_STATS` instância.</span><span class="sxs-lookup"><span data-stu-id="e8139-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="e8139-109">Esse número é definido como zero sempre que ocorre uma coleta de lixo de geração de zero.</span><span class="sxs-lookup"><span data-stu-id="e8139-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="e8139-110">O número de bytes promovidos para uma geração maior mais recente coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="e8139-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8139-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="e8139-111">Remarks</span></span>  
 <span data-ttu-id="e8139-112">[Getmemstats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) aceita um parâmetro de saída do tipo `COR_GC_THREAD_STATS`.</span><span class="sxs-lookup"><span data-stu-id="e8139-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8139-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8139-113">Requirements</span></span>  
 <span data-ttu-id="e8139-114">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8139-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8139-115">**Cabeçalho:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="e8139-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="e8139-116">**Biblioteca:** incluído como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="e8139-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8139-117">**Versões do .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8139-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8139-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e8139-118">See Also</span></span>  
 [<span data-ttu-id="e8139-119">Estruturas de hospedagem</span><span class="sxs-lookup"><span data-stu-id="e8139-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="e8139-120">Interface IHostTask</span><span class="sxs-lookup"><span data-stu-id="e8139-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
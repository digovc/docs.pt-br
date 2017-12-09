---
title: "Método ICLRTask::SwitchOut"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.SwitchOut
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 82fffd5de9735db51d9ea5f417c745736b98b53d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="9b18c-102">Método ICLRTask::SwitchOut</span><span class="sxs-lookup"><span data-stu-id="9b18c-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="9b18c-103">Notifica o common language runtime (CLR) que a tarefa representada pela atual [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instância não está em um estado operacional.</span><span class="sxs-lookup"><span data-stu-id="9b18c-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b18c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9b18c-104">Syntax</span></span>  
  
```  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9b18c-105">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="9b18c-105">Return Value</span></span>  
  
|<span data-ttu-id="9b18c-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9b18c-106">HRESULT</span></span>|<span data-ttu-id="9b18c-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b18c-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9b18c-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b18c-108">S_OK</span></span>|<span data-ttu-id="9b18c-109">`SwitchOut`retornou com êxito.</span><span class="sxs-lookup"><span data-stu-id="9b18c-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="9b18c-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9b18c-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9b18c-111">O CLR não foi carregado em um processo ou o CLR está em um estado em que ele não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="9b18c-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9b18c-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9b18c-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9b18c-113">A chamada foi atingido.</span><span class="sxs-lookup"><span data-stu-id="9b18c-113">The call timed out.</span></span>|  
|<span data-ttu-id="9b18c-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9b18c-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9b18c-115">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="9b18c-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9b18c-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9b18c-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9b18c-117">Um evento foi cancelado durante um thread bloqueado ou fibra estava aguardando nele.</span><span class="sxs-lookup"><span data-stu-id="9b18c-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9b18c-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9b18c-118">E_FAIL</span></span>|<span data-ttu-id="9b18c-119">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="9b18c-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9b18c-120">Quando um método retornará E_FAIL, o CLR não será mais utilizável dentro do processo.</span><span class="sxs-lookup"><span data-stu-id="9b18c-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9b18c-121">As chamadas subsequentes para hospedagem métodos retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9b18c-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b18c-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="9b18c-122">Remarks</span></span>  
 <span data-ttu-id="9b18c-123">Um host chama `SwitchOut` para informar ao CLR que ele interrompeu a execução da tarefa que atual `ICLRTask` instância representa e irá reagendar a tarefa.</span><span class="sxs-lookup"><span data-stu-id="9b18c-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b18c-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9b18c-124">Requirements</span></span>  
 <span data-ttu-id="9b18c-125">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b18c-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b18c-126">**Cabeçalho:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9b18c-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9b18c-127">**Biblioteca:** incluído como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="9b18c-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b18c-128">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b18c-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b18c-129">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9b18c-129">See Also</span></span>  
 [<span data-ttu-id="9b18c-130">Interface ICLRTask</span><span class="sxs-lookup"><span data-stu-id="9b18c-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="9b18c-131">Interface ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="9b18c-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="9b18c-132">Interface IHostTask</span><span class="sxs-lookup"><span data-stu-id="9b18c-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="9b18c-133">Interface IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="9b18c-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
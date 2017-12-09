---
title: Interface ICorDebugDataTarget
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugDataTarget
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugDataTarget
helpviewer_keywords: ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: df5f05be-bed7-4f3c-bc89-dbb435d79a0b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 030ad5e61d215bd840da5b16a56e4b8f8b7791ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget-interface"></a><span data-ttu-id="852b5-102">Interface ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="852b5-102">ICorDebugDataTarget Interface</span></span>
<span data-ttu-id="852b5-103">Fornece uma interface de retorno de chamada que oferece acesso a um determinado processo de destino.</span><span class="sxs-lookup"><span data-stu-id="852b5-103">Provides a callback interface that provides access to a particular target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="852b5-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="852b5-104">Methods</span></span>  
  
|<span data-ttu-id="852b5-105">Método</span><span class="sxs-lookup"><span data-stu-id="852b5-105">Method</span></span>|<span data-ttu-id="852b5-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="852b5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="852b5-107">Método GetPlatform</span><span class="sxs-lookup"><span data-stu-id="852b5-107">GetPlatform Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|<span data-ttu-id="852b5-108">Fornece informações sobre a plataforma, incluindo arquitetura de processador e sistema operacional, que está executando o processo de destino.</span><span class="sxs-lookup"><span data-stu-id="852b5-108">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>|  
|[<span data-ttu-id="852b5-109">Método ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="852b5-109">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|<span data-ttu-id="852b5-110">Obtém um bloco de memória contígua, iniciando no endereço especificado e o retorna no buffer fornecido.</span><span class="sxs-lookup"><span data-stu-id="852b5-110">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>|  
|[<span data-ttu-id="852b5-111">Método GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="852b5-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|<span data-ttu-id="852b5-112">Solicita o contexto do thread atual para o segmento especificado.</span><span class="sxs-lookup"><span data-stu-id="852b5-112">Requests the current thread context for the specified thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="852b5-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="852b5-113">Remarks</span></span>  
 <span data-ttu-id="852b5-114">`ICorDebugDataTarget`e seus métodos têm as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="852b5-114">`ICorDebugDataTarget` and its methods have the following characteristics:</span></span>  
  
-   <span data-ttu-id="852b5-115">Os serviços de depuração chamar métodos nessa interface para acessar a memória e outros dados no processo de destino.</span><span class="sxs-lookup"><span data-stu-id="852b5-115">The debugging services call methods on this interface to access memory and other data in the target process.</span></span>  
  
-   <span data-ttu-id="852b5-116">O cliente do depurador deve implementar essa interface conforme apropriado para o destino específico (por exemplo, um processo em tempo real ou um despejo de memória).</span><span class="sxs-lookup"><span data-stu-id="852b5-116">The debugger client must implement this interface as appropriate for the particular target (for example, a live process or a memory dump).</span></span>  
  
-   <span data-ttu-id="852b5-117">O `ICorDebugDataTarget` métodos podem ser chamados somente de dentro de métodos implementados em outros `ICorDebug*` interfaces.</span><span class="sxs-lookup"><span data-stu-id="852b5-117">The `ICorDebugDataTarget` methods can be invoked only from within methods implemented in other `ICorDebug*` interfaces.</span></span> <span data-ttu-id="852b5-118">Isso garante que o cliente de depurador tem controle sobre qual thread é invocada e quando.</span><span class="sxs-lookup"><span data-stu-id="852b5-118">This ensures that the debugger client has control over which thread it is invoked on, and when.</span></span>  
  
-   <span data-ttu-id="852b5-119">O `ICorDebugDataTarget` implementação deve sempre retornar informações atualizadas sobre o destino.</span><span class="sxs-lookup"><span data-stu-id="852b5-119">The `ICorDebugDataTarget` implementation must always return up-to-date information about the target.</span></span>  
  
 <span data-ttu-id="852b5-120">O processo de destino deve ser interrompido e não alterado de alguma forma ao `ICorDebug*` interfaces (e, portanto, `ICorDebugDataTarget` métodos) está sendo chamado.</span><span class="sxs-lookup"><span data-stu-id="852b5-120">The target process should be stopped and not changed in any way while `ICorDebug*` interfaces (and therefore `ICorDebugDataTarget` methods) are being called.</span></span> <span data-ttu-id="852b5-121">Se o destino é um processo em tempo real e suas alterações de estado, o [Iclrdebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) método deve ser chamado novamente para fornecer uma instância de ICorDebugProcess de substituição.</span><span class="sxs-lookup"><span data-stu-id="852b5-121">If the target is a live process and its state changes, the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method has to be called again to provide a replacement ICorDebugProcess instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="852b5-122">Esta interface não dá suporte a que está sendo chamado remotamente, entre computadores ou entre processos.</span><span class="sxs-lookup"><span data-stu-id="852b5-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="852b5-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="852b5-123">Requirements</span></span>  
 <span data-ttu-id="852b5-124">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="852b5-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="852b5-125">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="852b5-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="852b5-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="852b5-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="852b5-127">**Versões do .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="852b5-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="852b5-128">Consulte também</span><span class="sxs-lookup"><span data-stu-id="852b5-128">See Also</span></span>  
 [<span data-ttu-id="852b5-129">Interfaces de depuração</span><span class="sxs-lookup"><span data-stu-id="852b5-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="852b5-130">Depuração</span><span class="sxs-lookup"><span data-stu-id="852b5-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
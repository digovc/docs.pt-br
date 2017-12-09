---
title: "Método ICLRMetaHost::QueryLegacyV2RuntimeBinding"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.RequestRuntimeLoadedNotification
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::QueryLegacyV2RuntimeBinding
helpviewer_keywords:
- QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
- ICLRMetaHost::QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
ms.assetid: 9929817e-acc9-40b7-960c-598664e04b60
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c273a1690828e37c8f7fcf5071e42e5bb2c58228
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a><span data-ttu-id="e554a-102">Método ICLRMetaHost::QueryLegacyV2RuntimeBinding</span><span class="sxs-lookup"><span data-stu-id="e554a-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding Method</span></span>
<span data-ttu-id="e554a-103">Retorna uma interface que representa um tempo de execução para o qual a política de ativação herdadas foi associada, por exemplo, usando o `useLegacyV2RuntimeActivationPolicy` atributo no [ \<inicialização > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) entrada do arquivo de configuração, pelo uso direto de ativação herdada APIs, ou chamando o [Bindaslegacyv2runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="e554a-103">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e554a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e554a-104">Syntax</span></span>  
  
```  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e554a-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e554a-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="e554a-106">[in] Required.Currently é o único valor válido para este parâmetro `IID_ICLRRuntimeInfo`.</span><span class="sxs-lookup"><span data-stu-id="e554a-106">[in] Required.Currently the only valid value for this parameter is `IID_ICLRRuntimeInfo`.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="e554a-107">[out] Necessário.</span><span class="sxs-lookup"><span data-stu-id="e554a-107">[out] Required.</span></span> <span data-ttu-id="e554a-108">Quando este método retorna, contém um ponteiro para o [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface que representa um tempo de execução que foi associado à política de ativação herdadas.</span><span class="sxs-lookup"><span data-stu-id="e554a-108">When this method returns, contains a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that represents a runtime that has been bound to legacy activation policy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e554a-109">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="e554a-109">Return Value</span></span>  
 <span data-ttu-id="e554a-110">Este método retorna a seguintes HRESULTs específicos, bem como o HRESULT erros que indicam falha do método.</span><span class="sxs-lookup"><span data-stu-id="e554a-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e554a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e554a-111">HRESULT</span></span>|<span data-ttu-id="e554a-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="e554a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e554a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="e554a-113">S_OK</span></span>|<span data-ttu-id="e554a-114">O método foi concluída com êxito e retornou um tempo de execução que foi associado à política de ativação herdadas.</span><span class="sxs-lookup"><span data-stu-id="e554a-114">The method completed successfully and returned a runtime that was bound to legacy activation policy.</span></span>|  
|<span data-ttu-id="e554a-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e554a-115">S_FALSE</span></span>|<span data-ttu-id="e554a-116">O método foi concluída com êxito, mas um tempo de execução herdado não ainda estiver associado.</span><span class="sxs-lookup"><span data-stu-id="e554a-116">The method completed successfully, but a legacy runtime has not yet been bound.</span></span>|  
|<span data-ttu-id="e554a-117">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="e554a-117">E_NOINTERFACE</span></span>|<span data-ttu-id="e554a-118">O método encontrado um tempo de execução que foi associado à política de ativação herdadas, mas `riid` em tempo de execução que não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="e554a-118">The method found a runtime that was bound to legacy activation policy, but `riid` is not supported by that runtime.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e554a-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="e554a-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e554a-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e554a-120">Requirements</span></span>  
 <span data-ttu-id="e554a-121">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e554a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e554a-122">**Cabeçalho:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e554a-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e554a-123">**Biblioteca:** incluído como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="e554a-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e554a-124">**Versões do .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e554a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e554a-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e554a-125">See Also</span></span>  
 [<span data-ttu-id="e554a-126">Interface ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="e554a-126">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="e554a-127">Hospedagem</span><span class="sxs-lookup"><span data-stu-id="e554a-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
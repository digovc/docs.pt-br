---
title: "Método ICLRStrongName::StrongNameKeyDelete"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameKeyDelete
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyDelete method [.NET Framework hosting]
ms.assetid: 0163412f-f617-4428-89e0-03992fec31e8
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8fbb6af492007eb0dc2a9ea83c53e3559225428d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="bbb7a-102">Método ICLRStrongName::StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="bbb7a-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="bbb7a-103">Exclui o contêiner de chave especificado.</span><span class="sxs-lookup"><span data-stu-id="bbb7a-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbb7a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bbb7a-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bbb7a-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="bbb7a-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="bbb7a-106">[in] O nome do contêiner de chave para excluir.</span><span class="sxs-lookup"><span data-stu-id="bbb7a-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bbb7a-107">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="bbb7a-107">Return Value</span></span>  
 <span data-ttu-id="bbb7a-108">`S_OK`Se o método foi concluída com êxito; Caso contrário, um valor HRESULT que indica uma falha (consulte [valores HRESULT comuns](http://go.microsoft.com/fwlink/?LinkId=213878) para obter uma lista).</span><span class="sxs-lookup"><span data-stu-id="bbb7a-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbb7a-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="bbb7a-109">Remarks</span></span>  
 <span data-ttu-id="bbb7a-110">Use o [Strongnamekeyinstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) método para importar um par de chaves pública/privada para um contêiner.</span><span class="sxs-lookup"><span data-stu-id="bbb7a-110">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbb7a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bbb7a-111">Requirements</span></span>  
 <span data-ttu-id="bbb7a-112">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbb7a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbb7a-113">**Cabeçalho:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="bbb7a-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bbb7a-114">**Biblioteca:** incluído como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="bbb7a-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bbb7a-115">**Versões do .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbb7a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbb7a-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="bbb7a-116">See Also</span></span>  
 [<span data-ttu-id="bbb7a-117">Método StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="bbb7a-117">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="bbb7a-118">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="bbb7a-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
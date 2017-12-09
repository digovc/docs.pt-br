---
title: "Método IMetaDataImport::EnumInterfaceImpls"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumInterfaceImpls
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1d9f2883c32daafd8938bd1c80c035a3527cc6a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="74135-102">Método IMetaDataImport::EnumInterfaceImpls</span><span class="sxs-lookup"><span data-stu-id="74135-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="74135-103">Enumera MethodDef tokens que representam as implementações de interface.</span><span class="sxs-lookup"><span data-stu-id="74135-103">Enumerates MethodDef tokens representing interface implementations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74135-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="74135-104">Syntax</span></span>  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74135-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="74135-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="74135-106">[out no] Um ponteiro para o enumerador.</span><span class="sxs-lookup"><span data-stu-id="74135-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="74135-107">[in] O token de TypeDef cujo MethodDef tokens representando implementações de interface devem ser enumerados.</span><span class="sxs-lookup"><span data-stu-id="74135-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="74135-108">[out] A matriz usada para armazenar os tokens de MethodDef.</span><span class="sxs-lookup"><span data-stu-id="74135-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="74135-109">[in] O tamanho máximo da `rImpls` matriz.</span><span class="sxs-lookup"><span data-stu-id="74135-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="74135-110">[out] O número real de tokens retornados em `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="74135-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74135-111">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="74135-111">Return Value</span></span>  
  
|<span data-ttu-id="74135-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74135-112">HRESULT</span></span>|<span data-ttu-id="74135-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="74135-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="74135-114">`EnumInterfaceImpls`retornou com êxito.</span><span class="sxs-lookup"><span data-stu-id="74135-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="74135-115">Não há nenhum token MethodDef enumerar.</span><span class="sxs-lookup"><span data-stu-id="74135-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="74135-116">Nesse caso, `pcImpls` é definido como zero.</span><span class="sxs-lookup"><span data-stu-id="74135-116">In that case, `pcImpls` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="74135-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74135-117">Requirements</span></span>  
 <span data-ttu-id="74135-118">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74135-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74135-119">**Cabeçalho:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="74135-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="74135-120">**Biblioteca:** incluído como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="74135-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="74135-121">**Versões do .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74135-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74135-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="74135-122">See Also</span></span>  
 [<span data-ttu-id="74135-123">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="74135-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="74135-124">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="74135-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
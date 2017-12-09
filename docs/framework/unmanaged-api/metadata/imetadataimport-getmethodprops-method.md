---
title: "Método IMetaDataImport::GetMethodProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetMethodProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d02369f1e401f49548f4fdb0fc177dc7403654d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetmethodprops-method"></a><span data-ttu-id="72847-102">Método IMetaDataImport::GetMethodProps</span><span class="sxs-lookup"><span data-stu-id="72847-102">IMetaDataImport::GetMethodProps Method</span></span>
<span data-ttu-id="72847-103">Obtém os metadados associados com o método referenciado pelo MethodDef especificado token.</span><span class="sxs-lookup"><span data-stu-id="72847-103">Gets the metadata associated with the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72847-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="72847-104">Syntax</span></span>  
  
```  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72847-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="72847-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="72847-106">[in] O token MethodDef que representa o método para retornar metadados.</span><span class="sxs-lookup"><span data-stu-id="72847-106">[in] The MethodDef token that represents the method to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="72847-107">[out] Um ponteiro para um token de TypeDef que representa o tipo que implementa o método.</span><span class="sxs-lookup"><span data-stu-id="72847-107">[out] A Pointer to a TypeDef token that represents the type that implements the method.</span></span>  
  
 `szMethod`  
 <span data-ttu-id="72847-108">[out] Um ponteiro para um buffer que tem o nome do método.</span><span class="sxs-lookup"><span data-stu-id="72847-108">[out] A Pointer to a buffer that has the method's name.</span></span>  
  
 `cchMethod`  
 <span data-ttu-id="72847-109">[in] O tamanho solicitado de `szMethod`.</span><span class="sxs-lookup"><span data-stu-id="72847-109">[in] The requested size of `szMethod`.</span></span>  
  
 `pchMethod`  
 <span data-ttu-id="72847-110">[out] Um ponteiro para o tamanho em caracteres largos de `szMethod`, ou, no caso de truncamento, o número real de caracteres largos no nome do método.</span><span class="sxs-lookup"><span data-stu-id="72847-110">[out] A Pointer to the size in wide characters of `szMethod`, or in the case of truncation, the actual number of wide characters in the method name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="72847-111">[out] Um ponteiro para os sinalizadores associados ao método.</span><span class="sxs-lookup"><span data-stu-id="72847-111">[out] A pointer to any flags associated with the method.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="72847-112">[out] Um ponteiro para a assinatura de metadados de binários do método.</span><span class="sxs-lookup"><span data-stu-id="72847-112">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="72847-113">[out] Um ponteiro para o tamanho em bytes do `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="72847-113">[out] A Pointer to the size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="72847-114">[out] Um ponteiro para o endereço virtual relativo do método.</span><span class="sxs-lookup"><span data-stu-id="72847-114">[out] A pointer to the relative virtual address of the method.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="72847-115">[out] Um ponteiro para os sinalizadores de implementação para o método.</span><span class="sxs-lookup"><span data-stu-id="72847-115">[out] A pointer to any implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72847-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72847-116">Requirements</span></span>  
 <span data-ttu-id="72847-117">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72847-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72847-118">**Cabeçalho:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="72847-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="72847-119">**Biblioteca:** incluído como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="72847-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="72847-120">**Versões do .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72847-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72847-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="72847-121">See Also</span></span>  
 [<span data-ttu-id="72847-122">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="72847-122">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="72847-123">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="72847-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
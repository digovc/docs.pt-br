---
title: "Método ICorProfilerInfo::GetILFunctionBody"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetILFunctionBody
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6908b6c765a56ef0aa43a66cc58ec74b525bc2d3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="c5782-102">Método ICorProfilerInfo::GetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="c5782-102">ICorProfilerInfo::GetILFunctionBody Method</span></span>
<span data-ttu-id="c5782-103">Obtém um ponteiro para o corpo de um método no código do Microsoft intermediate language (MSIL), começando em seu cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="c5782-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5782-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c5782-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5782-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="c5782-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="c5782-106">[in] A ID do módulo no qual a função reside.</span><span class="sxs-lookup"><span data-stu-id="c5782-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="c5782-107">[in] O token de metadados para o método.</span><span class="sxs-lookup"><span data-stu-id="c5782-107">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="c5782-108">[out] Um ponteiro para o cabeçalho do método.</span><span class="sxs-lookup"><span data-stu-id="c5782-108">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="c5782-109">[out] Um inteiro que especifica o tamanho do método.</span><span class="sxs-lookup"><span data-stu-id="c5782-109">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5782-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="c5782-110">Remarks</span></span>  
 <span data-ttu-id="c5782-111">Um método é delimitado pelo módulo no qual ele reside.</span><span class="sxs-lookup"><span data-stu-id="c5782-111">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="c5782-112">Porque o `GetILFunctionBody` método é projetado para fornecer um acesso de ferramenta para o código MSIL antes de eles terem sido carregados pelo common language runtime (CLR), ele usa o token de metadados do método para localizar a instância desejada.</span><span class="sxs-lookup"><span data-stu-id="c5782-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 <span data-ttu-id="c5782-113">`GetILFunctionBody`pode retornar um HRESULT de CORPROF_E_FUNCTION_NOT_IL se o `methodId` aponta para um método sem qualquer MSIL de código (como um método abstrato ou uma plataforma de invocar o método de (PInvoke)).</span><span class="sxs-lookup"><span data-stu-id="c5782-113">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5782-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5782-114">Requirements</span></span>  
 <span data-ttu-id="c5782-115">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5782-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5782-116">**Cabeçalho:** Corprof. idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c5782-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c5782-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5782-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5782-118">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5782-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5782-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c5782-119">See Also</span></span>  
 [<span data-ttu-id="c5782-120">Interface ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="c5782-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
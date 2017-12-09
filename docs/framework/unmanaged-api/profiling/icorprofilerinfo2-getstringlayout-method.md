---
title: "Método ICorProfilerInfo2::GetStringLayout"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetStringLayout
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 52a1b9218feb76f7653f747aa52c44284293221f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="1802d-102">Método ICorProfilerInfo2::GetStringLayout</span><span class="sxs-lookup"><span data-stu-id="1802d-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="1802d-103">Obtém informações sobre o layout de um objeto de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1802d-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="1802d-104">Esse método foi preterido no [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]e é substituído pelo [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="1802d-104">This method is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], and is superseded by the [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1802d-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1802d-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1802d-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1802d-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="1802d-107">[out] Um ponteiro para o deslocamento do local, relativo para o `ObjectID` ponteiro, que armazena o comprimento da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1802d-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="1802d-108">O comprimento é armazenado como um `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="1802d-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1802d-109">Este parâmetro retorna o comprimento da cadeia de caracteres em si, não o comprimento do buffer.</span><span class="sxs-lookup"><span data-stu-id="1802d-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="1802d-110">O comprimento do buffer não está mais disponível.</span><span class="sxs-lookup"><span data-stu-id="1802d-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="1802d-111">[out] Um ponteiro para o deslocamento do local, relativo para o `ObjectID` ponteiro, que armazena o comprimento da cadeia de caracteres em si.</span><span class="sxs-lookup"><span data-stu-id="1802d-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="1802d-112">O comprimento é armazenado como um `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="1802d-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="1802d-113">[out] Um ponteiro para o deslocamento do buffer, relativo para o `ObjectID` ponteiro, que armazena a cadeia de caracteres largos.</span><span class="sxs-lookup"><span data-stu-id="1802d-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1802d-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="1802d-114">Remarks</span></span>  
 <span data-ttu-id="1802d-115">O `GetStringLayout` método obtém os deslocamentos, relativo ao `ObjectID` ponteiro dos locais em que é armazenada a seguir:</span><span class="sxs-lookup"><span data-stu-id="1802d-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
-   <span data-ttu-id="1802d-116">O comprimento do buffer da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1802d-116">The length of the string's buffer.</span></span>  
  
-   <span data-ttu-id="1802d-117">O comprimento da cadeia de caracteres em si.</span><span class="sxs-lookup"><span data-stu-id="1802d-117">The length of the string itself.</span></span>  
  
-   <span data-ttu-id="1802d-118">O buffer que contém a cadeia de caracteres largos de real.</span><span class="sxs-lookup"><span data-stu-id="1802d-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="1802d-119">Cadeias de caracteres podem ser terminada em nulo.</span><span class="sxs-lookup"><span data-stu-id="1802d-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1802d-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1802d-120">Requirements</span></span>  
 <span data-ttu-id="1802d-121">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1802d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1802d-122">**Cabeçalho:** Corprof. idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1802d-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1802d-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1802d-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1802d-124">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1802d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1802d-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1802d-125">See Also</span></span>  
 [<span data-ttu-id="1802d-126">Interface ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="1802d-126">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="1802d-127">Interface ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="1802d-127">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)